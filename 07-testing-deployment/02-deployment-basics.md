# Deployment Basics 🚀

Deployment is the process of putting your code on a server so the world can use it.

## "It works on my machine" vs. Production
Locally, you run `localhost`. In production, you need:
-   A public IP address or Domain Name.
-   A server that is always on.
-   Security (HTTPS/SSL).

## Where to Deploy?

### 1. PaaS (Platform as a Service) - *Easiest*
They handle the servers, you just push code.
-   **Render / Railway / Fly.io**: Great free tiers, easy setup.
-   **Heroku**: Classic choice, but mostly paid now.

### 2. IaaS (Infrastructure as a Service) - *Most Control*
You rent a virtual computer (VM) and set up everything.
-   **AWS EC2, Google Compute Engine, DigitalOcean Droplets**.
-   *Harder*: You manage OS updates, security patches, etc.

## Key Concepts

### Environment Variables (.env)
**NEVER** commit secrets (API keys, DB passwords) to GitHub.
Use environment variables on the server to store them securely.

### CI/CD (Continuous Integration / Continuous Deployment)
Automating the release process.
1.  You push code to GitHub.
2.  GitHub Actions runs your tests (CI).
3.  If tests pass, it automatically deploys to the server (CD).

### Docker 🐳
Packages your app and everything it needs (OS, libraries) into a container.
Ensures it runs exactly the same on your laptop and the server.
