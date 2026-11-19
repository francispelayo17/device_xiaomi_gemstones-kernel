# 📥 ChicKernel permalinks
- [**GitHub Releases**](https://github.com/chickendrop89/device_xiaomi_unified-kernel/releases/latest)
- [**SourceForge mirror**](https://sourceforge.net/projects/chickernel-xiaomi-tapas-kernel)
- [**XDA Forums thread**](https://xdaforums.com/t/kernel-chickernel-a-kernel-optimized-for-smoothness-and-low-memory.4678538) 

# 📝 Note:
This kernel is tuned for these SDM685 (`sm6225-AD`) devices with `4/6GB` RAM:
- Xiaomi Redmi Note _12_ 4G (`topaz` / `tapas`)
- Xiaomi Redmi Note _13_ 4G (`sapphire` / `sapphiren`)

If your device is not on the list and has a compatible KMI,                
it is not recommended nor supported as the kernel is stripped down
to support this specific `SoC` and `OEM`.

# ⛔ Report Issues
Please [report issues here](https://github.com/chickendrop89/device_xiaomi_unified-recovery/issues), or to [my telegram](https://t.me/chickendrop89)

# 🏗️ Build notes:
For building, upstreaming `KSU-Next`/`SuSFS`, automated builds using actions, [view this wiki](https://github.com/chickendrop89/device_xiaomi_unified-kernel/wiki/Build-notes)

# 🤖 GitHub Actions build:
To customize the kernel name, edit [`kernel-name.txt`](./kernel-name.txt) in the repository root and commit the change. The name is used in the AnyKernel installer display, ZIP filenames, and Telegram captions. Then run **Build and Send Kernel** from the repository's Actions tab and choose a build variant. Select one variant for a faster build, or `all` to build all three. Before building, it updates KernelSU-Next from the official [KernelSU-Next repository](https://github.com/KernelSU-Next/KernelSU-Next), using its `dev` branch, then uploads the ZIP files as workflow artifacts and sends them to Telegram.

Before running it, add these repository Actions secrets:
- `TELEGRAM_BOT_TOKEN`: the token from BotFather
- `TELEGRAM_CHAT_ID`: the destination chat ID; make sure the bot can post in that chat

# 🏗️ Kernel quirks
For any other kernel developers out there. 

Here are some highlights of device-specific issues that i have found a fix to on this kernel:

- Fixed fuel gauge (`sm5602`) and USB (`dwc3-msm-core`) not working after merging `5.15.149` 
  - [2b14b93963328af3fb023c02c9c8a705a71eb8a7](https://github.com/chickendrop89/device_xiaomi_gemstones-kernel/commit/2b14b93963328af3fb023c02c9c8a705a71eb8a7)
- Fixed kernel panicking on USB tethering
  - [082c1c5974a03663cf955459aef88da8789b2238](https://github.com/chickendrop89/device_xiaomi_gemstones-kernel/commit/082c1c5974a03663cf955459aef88da8789b2238)
- Fixed `mi_thermald` misconfigured to turn off wrong cores
  - [3e85c4293b4dd4b67e084e3e40ca70a978c1f2c8](https://github.com/chickendrop89/device_xiaomi_gemstones-kernel/commit/3e85c4293b4dd4b67e084e3e40ca70a978c1f2c8)
- Suppresed vendor `kmsg` spam/debugging of modules without source
  - [06af5ac88a95e9ccc2fcd5faacff1f103c356afd](https://github.com/chickendrop89/device_xiaomi_gemstones-kernel/commit/06af5ac88a95e9ccc2fcd5faacff1f103c356afd) | [3cc1c](https://github.com/chickendrop89/device_xiaomi_gemstones-kernel/commit/3cc1c53a2471d42936383a654d2fd0451dc556a9) | [e6036](https://github.com/chickendrop89/device_xiaomi_gemstones-kernel/commit/e6036fddf42258ac02c7ed65362ec4ce196e6872) | [57c46](https://github.com/chickendrop89/device_xiaomi_gemstones-kernel/commit/57c46727a3a4d58e1b516bed30ccb0bec944b167)
  
