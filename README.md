# 🐾 CpuLeash

> A lightweight Windows CLI tool to hard-cap CPU usage of any running process using Job Objects.

![Platform](https://img.shields.io/badge/platform-Windows%208%2B-blue)
![Language](https://img.shields.io/badge/language-C%2B%2B-informational)
![License](https://img.shields.io/badge/license-MIT-green)

---

## What it does

CpuLeash attaches one or more running processes to a Windows Job Object and enforces a hard CPU rate cap preventing them from consuming more than a specified percentage of CPU time.

---

## Usage

```
CpuLeash <pid> [<pid> ...] <percentage>
```

**Examples:**

```bash
# Limit process 1234 to 30% CPU
CpuLeash 1234 30

# Limit multiple processes to 50% CPU
CpuLeash 1234 5678 50
```

> Press `ENTER` to release the limit and exit.

---

## Requirements

- Windows 8 or later
- Visual Studio (to build)

---

## Building

1. Clone the repo
2. Open `CpuLeash.sln` in Visual Studio
3. Build -> Release

---

## How it works

CpuLeash uses the Windows [Job Object API](https://learn.microsoft.com/en-us/windows/win32/procthread/job-objects) with `JOBOBJECT_CPU_RATE_CONTROL_INFORMATION` and the `JOB_OBJECT_CPU_RATE_CONTROL_HARD_CAP` flag to enforce strict CPU limits at the OS level.

---

## License

MIT
