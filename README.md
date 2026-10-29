# PulseWatch — Service Status & Uptime Monitoring

PulseWatch is a platform for monitoring website and API availability while keeping users informed about service health. It combines uptime checks, public status pages, incident communication, and infrastructure configuration in one place.

Designed for both hosted and self-managed environments, PulseWatch helps teams detect service disruptions, communicate incidents, and maintain visibility into application reliability.

## Overview

- **Unified Monitoring:** Manage uptime checks and status pages from one platform.
- **Global Probes:** Monitor services from multiple geographic regions.
- **Custom Status Pages:** Publish service health updates using customizable status pages.
- **Incident Notifications:** Notify subscribers and teams about outages, maintenance, and recovery.
- **Infrastructure as Code:** Configure monitoring resources through code and automation tools.
- **Self-Hosting:** Run the platform using container-based deployment options.

## Core Features

### Status Pages

Create public or protected status pages to communicate service availability and ongoing incidents. Customize the presentation, configure custom domains, schedule maintenance windows, and allow subscribers to receive updates.

### Uptime Monitoring

Monitor websites, servers, and APIs for availability and response performance. Checks from multiple regions help identify service disruptions and distinguish regional issues from broader outages.

### Incident Communication

Keep users and engineering teams informed through supported notification channels, including email, Slack, Discord, PagerDuty, and webhooks. Available integrations depend on the configured deployment and plan.

### Monitoring as Code

Manage monitoring configurations through YAML, command-line tools, GitHub Actions, and Terraform. This approach makes configurations easier to version, review, reproduce, and integrate into development workflows.

### API and Developer Tooling

Interact with monitoring resources through a typed API and developer tools. Command-line access and infrastructure integrations support automated workflows, while an MCP server can connect compatible AI assistants to supported operations.

## Getting Started

### Option 1: Docker Compose

Docker Compose provides a convenient way to start the project's services for local development or self-hosting.

```bash
# Copy the example environment configuration
cp .env.docker.example .env.docker

# Start the services
docker compose up -d
```

Once the services are running, the original project configuration exposes the following local interfaces:

- Dashboard: `http://localhost:3002`
- Status pages: `http://localhost:3003`

Check the repository's Docker deployment guide for environment variables, persistent storage, and troubleshooting instructions.

### Option 2: Self-Hosting

The application can be deployed using supported container images and compatible hosting platforms. Review the deployment documentation to configure the required services, environment variables, databases, and networking.

### Option 3: Manual Development Setup

**Requirements**

- Node.js 20 or later
- pnpm 10.26 or later
- Bun
- Deno
- Turso CLI

Install dependencies from the repository root:

```bash
pnpm install
```

Start the status page development server:

```bash
pnpm -w dev:status-page
```

Start the marketing website development server:

```bash
pnpm -w dev:web
```

For dashboard setup, database initialization, authentication, and environment configuration, follow the instructions in the relevant application README files.

## Technology Stack

| Technology | Purpose |
|---|---|
| Next.js | Dashboard and web application |
| Hono | API server |
| Go | Monitoring checker |
| Turso | Database infrastructure |
| Drizzle ORM | Database access and queries |
| Tinybird | Analytics |
| Tailwind CSS | Styling and layout |
| shadcn/ui | Interface components |

## Deployment and Configuration

Before deploying to production:

1. Configure the required environment variables and secrets.
2. Set up the database and any supporting services.
3. Configure monitoring regions and notification integrations.
4. Enable persistent storage where required.
5. Set up HTTPS, domains, and access controls.
6. Verify monitoring checks, incident notifications, and status-page updates.
7. Review the repository's license and deployment requirements.

## Documentation

Consult the repository's existing documentation for detailed installation, configuration, and deployment instructions. Keep commands, service addresses, and environment-variable names aligned with the actual implementation.

---

PulseWatch provides a foundation for combining uptime monitoring, incident communication, and service transparency in a single workflow.