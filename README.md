# 🛡️ argus - Your Command Center for Code Reviews

[![Download Now](https://img.shields.io/badge/Download-argus-2ea44f?style=for-the-badge)](https://github.com/bryan001207/argus)

## 👋 Welcome to argus

Are you an engineering lead drowning in pull requests, review requests, and security alerts? argus is here to rescue you. Think of it as your personal mission control for GitHub - a single, clean dashboard that shows you exactly what needs your attention, without any noise.

## 🔍 What Does argus Do?

argus gives you a bird's-eye view of your GitHub activity in real-time. It's like having a super-organized assistant who never sleeps and never misses a detail. Here's what you'll see at a glance:

- **Reviews Waiting on You** - No more hunting through emails. See every pull request that's waiting for your approval.
- **Merge-Ready PRs** - Spot the work that's ready to ship, so you can keep momentum going.
- **Stale Work** - Identify projects that have gone quiet and need a nudge.
- **Security Alerts** - Stay ahead of vulnerabilities before they become problems.

## 🏠 Self-Hosted and Private

Your code review data stays yours. argus runs entirely on your own machine - nothing is hosted externally, and you control everything with your own GitHub token. No third-party servers, no data sharing, just you and your repository data.

## 📋 What You'll Need

- A Windows computer (this guide covers Windows setup)
- A GitHub account
- Docker Desktop installed on your computer
- Your GitHub personal access token (we'll show you how to get one)

## 🚀 Getting Started

Let's get you up and running. Follow these steps carefully, and you'll have argus live in about 10 minutes.

### Step 1: Download argus

Visit this link to download the application: [https://github.com/bryan001207/argus](https://github.com/bryan001207/argus)

### Step 2: Create Your GitHub Token

1. Log in to your GitHub account
2. Click your profile picture (top-right corner) and select **Settings**
3. Scroll down and click **Developer settings** (bottom of the left sidebar)
4. Click **Personal access tokens** and then **Tokens (classic)**
5. Click **Generate new token** and then **Generate new token (classic)**
6. Give your token a name (like "argus-dashboard")
7. Set the expiration to 90 days (you can renew it later)
8. Under **Select scopes**, check these boxes:
   - `repo` (full control of private repositories)
   - `read:org` (read organization data)
   - `read:user` (read user profile data)
9. Click **Generate token** at the bottom
10. **Copy the token immediately** - GitHub only shows it once. Save it somewhere safe.

### Step 3: Install Docker Desktop

If you don't have Docker Desktop already:
1. Go to [docker.com](https://www.docker.com/products/docker-desktop/)
2. Download Docker Desktop for Windows
3. Run the installer and follow the on-screen instructions
4. Once installed, launch Docker Desktop and wait for it to finish starting up (you'll see a whale icon in your system tray when it's ready)

### Step 4: Launch argus

1. Open **Command Prompt** (press `Windows key`, type "cmd", and press Enter)
2. Copy and paste this command, then press Enter:

```
docker run -d --name argus -p 8080:8080 -e GITHUB_TOKEN=your_token_here bryan001207/argus
```

3. Replace `your_token_here` with the GitHub token you created in Step 2
4. Press Enter and wait a moment

### Step 5: Open Your Dashboard

1. Open your web browser (Chrome, Edge, or Firefox)
2. Go to `http://localhost:8080`
3. You're in! Welcome to your new engineering command center.

## 🎨 Features That Make Your Life Easier

### Real-Time Updates
argus refreshes automatically, so you always see the current state of your repos. No more manual refreshing or guessing.

### Simple, Clean Interface
You don't need to be a tech wizard to use argus. The dashboard is designed to be intuitive - if you can read a list, you can use argus.

### Privacy First
Everything runs locally on your machine. Your code, your data, your control.

## 🤔 Frequently Asked Questions

**Q: Do I need to install anything besides Docker?**
A: No. Docker handles everything. argus comes as a single container with all its dependencies included.

**Q: Can I share this with my team?**
A: Yes, but it's designed as a personal tool. Each person would run their own instance with their own GitHub token.

**Q: What happens when my token expires?**
A: You'll need to create a new token and restart argus with the new token. It takes about a minute.

**Q: Is this safe for private repositories?**
A: Absolutely. Your token only gives argus read-only access, and everything stays on your machine.

## 🛠️ Troubleshooting Common Issues

### Docker won't start
- Make sure Docker Desktop is fully running (whale icon in system tray)
- Try restarting Docker Desktop
- Check that Windows Hyper-V is enabled in your BIOS

### Token not working
- Double-check you copied the entire token
- Ensure you selected all the required scopes (Step 2, item 8)
- Try generating a new token if it's still not working

### Port already in use
- If port 8080 is busy, change the first `8080` in the command to something else, like `8081`
- Then access argus at `http://localhost:8081`

## 💡 Pro Tips

1. **Bookmark your dashboard** - You'll visit it multiple times a day
2. **Set a reminder** - Renew your GitHub token before it expires
3. **Check security alerts first** - They're usually the most time-sensitive

## 📊 What You'll See Daily

Your dashboard gives you a snapshot of:
- **Priority Queue** - Reviews that need your input right now
- **Ready to Ship** - PRs that have passed all checks
- **Falling Behind** - Work items that haven't had activity in a while
- **Security Status** - Any vulnerabilities that need attention

## 🔒 Your Data Stays Yours

We can't stress this enough - argus is self-hosted. There's no cloud service, no telemetry, no analytics. Your GitHub data travels from GitHub directly to your browser through your local Docker container. That's it.

## 🆘 Need Help?

If you get stuck:
- Check the repository documentation
- Look through existing issues on the project page
- Consult Docker's official documentation for Windows-specific problems

## 📝 Final Checklist

Before you start:
- [ ] Docker Desktop installed and running
- [ ] GitHub token created with correct permissions
- [ ] Internet connection active
- [ ] Port 8080 available (or use a different port)

## 🎉 You're Ready!

You now have a professional-grade GitHub dashboard that gives you complete visibility into your engineering workflow. Welcome to a more organized, productive way to lead your team.

Remember: argus is a tool for humans, by humans. It's built to simplify your life, not complicate it. Start with the basics, explore the interface, and soon you'll wonder how you ever managed without it.

Happy reviewing, engineering lead!

Keywords: code-review, dashboard, developer-tools, docker, engineering-management, github-api, golang, jira, pull-requests, react, self-hosted, typescript