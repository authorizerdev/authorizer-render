# Authorizer on Render

Deploy production ready [authorizer.dev](https://authorizer.dev) instance on [Render](https://render.com/) with a managed PostgreSQL database and build with it in 30seconds

[![Deploy to Render](https://render.com/images/deploy-to-render-button.svg)](https://render.com/deploy?repo=https://github.com/authorizerdev/authorizer-render)

After clicking the above button, follow the steps mentioned below:

### Step 1: Enter app details

Enter the name for your instance.

> Note: Optionally you can choose to deploy a branch `without-postgres` and configure database env, if you already have a postgres instance running.

### Step 2: Configure Required Variables

Authorizer v2 requires the following variables. Configure them in Render's environment settings:

| Variable | Description | Example |
| -------- | ----------- | ------- |
| `DATABASE_TYPE` | Database type | `postgres` |
| `DATABASE_URL` | Database connection string | *(auto-configured by Render)* |
| `JWT_TYPE` | JWT signing algorithm | `HS256` |
| `JWT_SECRET` | JWT signing secret | `test` |
| `ADMIN_SECRET` | Admin secret for admin operations | `admin` |
| `CLIENT_ID` | Client identifier **(required)** | `123456` |
| `CLIENT_SECRET` | Client secret **(required)** | `secret` |

These are mapped to CLI flags at startup. Please refer to the [server configuration docs](https://docs.authorizer.dev/core/server-config) for all available flags.

## Notes

- Source repo: https://github.com/authorizerdev/authorizer
- Docs: https://docs.authorizer.dev/deployment/render/

### Updating Authorizer on existing Render instance

- You can update the [docker image](https://github.com/authorizerdev/authorizer-render/blob/main/Dockerfile#L2) to the desired version in your repository which gets created with your deployment.

- You can find all the versions on [github](https://github.com/authorizerdev/authorizer/releases) or [dockerhub](https://hub.docker.com/r/lakhansamani/authorizer)
