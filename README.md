# Three MCP Projects for ChatGPT

[简体中文](README.zh-CN.md)

This is a lightweight entry page for three independent, experimental MCP projects covering Douyin and Creator Center, Windows PCs, and Android phones.

They were primarily organized for use with ChatGPT, although other compatible MCP clients can follow each project's own documentation.

This is not a bundled codebase, a monorepo, a new framework, or a brand. Each project keeps its own source code, releases, versioning, license, security boundaries, and issue tracker. Choose only the project you need; there is no requirement to install all three.

> These are independent community projects. They are not official projects of OpenAI, ChatGPT, Douyin, ByteDance, Android, or Microsoft.

## How the three projects happened

There was never an original plan to build a three-project collection.

The first MVP was very small: I only wanted ChatGPT to look through my own saved Douyin videos. More features were added gradually during real use, including reading posts and comments, viewing Creator Center, replying to comments, and publishing content.

Douyin's web interface changes frequently, and some operations can also trigger platform risk controls. Structured identification, post-action readback, and safety checks reduce mistakes, but they cannot guarantee that every operation will remain stable across page states, account environments, and platform changes.

A Windows desktop bridge was then built to make the Douyin project easier to debug and to provide a general fallback when a specialized route was unavailable. Later, curiosity led to an Android phone-control MCP.

The funny part is that the desktop bridge and phone-control project—originally created for debugging, fallback, or simple curiosity—often turned out to be smoother and more broadly useful in everyday tasks. Douyin is also fundamentally phone-first, so many actions feel more natural when performed directly on Android.

That does not make the specialized Douyin project obsolete. Generic desktop and phone control usually works one visible step at a time, while Douyin Controlled MCP can read structured state. For reviewing many Creator Center comments, filtering content, and identifying an exact post or comment target, that structured access is still much more convenient than screenshots and coordinate clicks alone.

All three projects are therefore published independently. Use whichever one matches the task; installing all of them is optional.

## Which one should I choose?

| Scenario | Recommended project | Main advantage |
| --- | --- | --- |
| Douyin and Creator Center | **Douyin Controlled MCP** | Structured access to posts, comments, and Creator Center state, especially for reviewing and filtering multiple backend comments |
| Windows PC | **AI Desktop Control Bridge** | Files, terminal, processes, screenshots, and safety-gated visible desktop control |
| Android phone | **Android Remote Control MCP** | Direct access to apps, screen, touch, text, files, and selected device capabilities |

### Douyin Controlled MCP

Useful for:

- viewing your own saved Douyin content, posts, and comments;
- reviewing multiple Creator Center comments in one place;
- replying to an explicitly identified comment;
- publishing only after owner confirmation;
- preferring structured target identification over visual clicking alone.

It is not intended to be an unattended account-operations system. Douyin page structure, account conditions, and risk controls may change, and some functions may need future adaptation.

### AI Desktop Control Bridge

Useful for:

- reading and editing local files;
- running terminal commands;
- starting, stopping, or inspecting processes;
- reading windows, screenshots, and visible UI state;
- operating allowlisted Windows applications;
- installing, testing, diagnosing, and repairing the other two projects.

The desktop bridge is both a standalone Windows tool and a local maintenance entry point for Douyin Controlled MCP and Android Remote Control MCP.

### Android Remote Control MCP

Useful for:

- operating Android apps directly;
- tapping, swiping, typing, and reading screen state;
- working with files, apps, notifications, and selected device capabilities;
- completing tasks that naturally belong on a phone;
- avoiding dependence on a desktop web interface or a permanently attached ADB session.

The MCP server runs directly on Android. When local troubleshooting is needed, the owner can connect the phone over USB, approve debugging, and let an AI connected through the desktop bridge inspect ADB state, installation, permissions, service configuration, and redacted logs.

## Recommended installation and repair order

You may install only the project you need.

For long-term use, or when you want an AI to diagnose and repair local problems later, connecting **AI Desktop Control Bridge** first is recommended.

Once the desktop bridge is working, an AI can—within the device owner's authorization:

- read and edit project files;
- run install, build, test, and diagnostic commands;
- inspect processes, windows, logs, and the local environment;
- repair Douyin Controlled MCP code or configuration;
- inspect the Android project through ADB after the phone is connected over USB;
- make a minimal fix for a specific error and run the relevant tests again.

Sensitive actions still belong to the device owner, including sign-in, passwords, OTPs, biometrics, payments, system permissions, USB debugging approval, and other security confirmations.

Do not allow multiple AI conversations to control the same mouse and keyboard, browser session, or phone at the same time.

## Let your own AI install and repair it

Each project aims to include documentation that an AI can read for installation, configuration, testing, and troubleshooting.

After opening the repository you need, you can give an AI coding assistant a prompt like this:

> Read the repository's README, AI setup, security, and troubleshooting documentation in full. Install and configure it on this device.
>
> If an error occurs, inspect the local environment, dependencies, configuration, and redacted logs first. Then read the relevant code, make the smallest reasonable fix, and run the project's own tests.
>
> Do not commit passwords, tokens, cookies, browser profiles, machine-specific endpoints, private conversations, or unredacted logs.
>
> Pause when sign-in, OTPs, biometrics, payments, USB debugging authorization, sensitive permissions, or another owner-only action is required, and tell me exactly what I need to do.
>
> Do not solve the problem by disabling safety checks, bypassing platform restrictions, or blindly repeating high-risk actions.

If the desktop bridge is already connected:

> Use the desktop bridge to investigate the current project error. Read the repository documentation and relevant code, inspect dependencies, configuration, and logs, make the smallest necessary fix, and run the tests. Do not change unrelated behavior or commit machine-private information.

For Android troubleshooting, connect the phone over USB and approve debugging first:

> The phone is connected over USB. Follow the repository documentation to inspect ADB, installation state, permissions, and MCP service configuration. Collect redacted logs and repair the current problem. I will personally handle lock-screen credentials, biometrics, account sign-in, and permission confirmations.

## Create a local startup script

After the desktop bridge works for the first time, ask the AI to create a **machine-specific startup and status-check script** on the desktop. This makes it easier to restore the environment after a reboot.

The script can:

- check required runtimes and dependencies;
- start the desktop bridge and its local components;
- show current status and connection information;
- inspect ports, processes, and basic configuration;
- point to useful logs when startup fails;
- provide stop and restart commands.

A short local note can also record:

- the local installation path;
- the correct startup order;
- how to check status;
- common log locations;
- stop and emergency-interrupt procedures;
- which script to run after rebooting the computer.

Suggested prompt:

> The desktop bridge is working. Based on the actual installation paths on this machine, create a machine-specific startup and status-check script on the desktop so the environment can be restored after a reboot.
>
> The script should check dependencies, start the services, show status and log locations, and provide stop or restart commands. Do not write tokens, cookies, passwords, private connection URLs, or other credentials directly into the desktop script. Keep sensitive configuration in the project's ignored private configuration location.

The desktop script and local note belong only to that machine. They should not be committed to a public repository and must not contain credentials.

## What to do when you find a bug

These projects are experimental Alpha software and cannot pre-cover every browser, Android device, vendor ROM, VPN, driver, network, and account environment.

Recommended process:

1. Give your AI the repository URL, exact error, reproduction steps, and redacted logs.
2. Ask it to read the latest README, setup, security, and known-issues documentation.
3. Inspect dependencies, configuration, processes, network state, and permissions.
4. If it is a code issue, make the smallest necessary fix.
5. Run the repository's type checks, builds, tests, or local acceptance scripts.
6. Confirm that the fix does not expose private configuration or weaken safety boundaries.
7. If it is a general reproducible problem, prepare a clear issue or pull request.

Once the desktop bridge is connected, it should provide most of the local capabilities needed to inspect source files, modify code, run tests, and troubleshoot the phone through USB.

For that reason, bugs should first be handled by the user's own AI using the repository documentation and local environment. The project author does not provide individual fallback support for every computer, phone, network, proxy, or account setup.

## Safety boundaries

All three projects should be treated as experimental Alpha software.

Before use, read the target project's own security documentation and follow these rules:

- passwords, OTPs, biometrics, payments, and identity verification must be handled by the device owner;
- sign-in, permission grants, and sensitive settings require owner confirmation;
- do not publish cookies, access tokens, browser profiles, private conversations, or unredacted logs;
- do not allow multiple AI conversations to control the same browser, mouse and keyboard, or phone;
- prefer structured state and post-action readback;
- use screenshots and coordinate clicking only as a fallback;
- do not bypass operating-system security boundaries, platform risk controls, or account restrictions;
- users are responsible for complying with platform rules and applicable law.

These tools must not be used with accounts, devices, or data without authorization.

## Maintenance expectations

These projects are published so users can give the repository to their own AI and use the documentation for self-service installation, configuration, debugging, and local repair.

Maintenance is best-effort:

- no per-device remote installation service is provided;
- compatibility is not guaranteed for every browser, Android version, vendor ROM, VPN, driver, or account environment;
- no fixed response time is promised;
- unreproducible personal-environment problems are not individually supported;
- platform UI, risk controls, or system behavior may change and require the user's AI to adapt the local project;
- users should not depend on the author to provide a custom repair for an individual machine.

General reproducible problems may still be submitted as well-documented, privacy-safe issues or pull requests.

## Upstream work and licenses

Each project keeps its own source attribution, license, third-party notices, and security documentation:

- **AI Desktop Control Bridge** is a derivative fork of [Desktop Commander MCP](https://github.com/wonderwhy-er/DesktopCommanderMCP);
- **Android Remote Control MCP** is derived from [android-remote-control-mcp](https://github.com/danielealbano/android-remote-control-mcp);
- **Douyin Controlled MCP** documents its own origin, third-party components, and security boundaries in its repository.

Before redistributing, modifying, or integrating a project, follow the license and documentation in that project's repository.

This entry repository only provides descriptions and links. It does not replace or combine the three projects' licenses.

## Project links

### Douyin Controlled MCP

Structured reading and careful operation for Douyin and Creator Center, especially for reviewing, filtering, and handling multiple backend comments.

- Repository: <https://github.com/mei-shui-xing/douyin-controlled-mcp>
- AI setup: <https://github.com/mei-shui-xing/douyin-controlled-mcp/blob/main/AI_SETUP.md>

### AI Desktop Control Bridge

Windows files, terminal, processes, screenshots, and safety-gated visible desktop control, plus a local maintenance entry point for the other projects.

- Repository: <https://github.com/mei-shui-xing/ai-desktop-control-bridge>
- Chinese README: <https://github.com/mei-shui-xing/ai-desktop-control-bridge/blob/main/README.zh-CN.md>

### Android Remote Control MCP

An MCP server running directly on Android for apps, screen, touch, text, files, and selected device capabilities.

- Repository: <https://github.com/mei-shui-xing/android-remote-control-mcp>
- Chinese README: <https://github.com/mei-shui-xing/android-remote-control-mcp/blob/main/README.zh-CN.md>
- Alpha APK: <https://github.com/mei-shui-xing/android-remote-control-mcp/releases/tag/v0.1.0-alpha>
