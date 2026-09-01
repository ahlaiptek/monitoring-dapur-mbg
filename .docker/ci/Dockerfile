FROM docker.io/oven/bun:1.4

WORKDIR /app
COPY . .

RUN bun install
RUN bun run build

EXPOSE 80
CMD ["bun", "run", "dev", "--host"]