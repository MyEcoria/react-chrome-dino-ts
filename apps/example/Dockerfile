
FROM node:20-alpine AS builder
RUN corepack enable && corepack prepare pnpm@latest --activate
WORKDIR /app
COPY package.json pnpm-lock.yaml pnpm-workspace.yaml ./
COPY packages/tsconfig-dino ./packages/tsconfig-dino
COPY packages/eslint-config-dino ./packages/eslint-config-dino
COPY packages/react-chrome-dino-ts ./packages/react-chrome-dino-ts
COPY apps/example/package.json ./apps/example/
RUN pnpm install --frozen-lockfile
COPY apps/example ./apps/example
RUN pnpm --filter react-chrome-dino-ts build
RUN pnpm --filter example build

FROM nginx:alpine-slim
COPY --from=builder /app/apps/example/dist /usr/share/nginx/html
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
