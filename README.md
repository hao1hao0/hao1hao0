import os
import psutil
import subprocess
import time

def kill_roblox_mutex():
    """ 关闭 Roblox 的互斥锁（Mutex），防止它强制关闭其他实例 """
    for proc in psutil.process_iter():
        try:
            if "RobloxPlayerBeta.exe" in proc.name():
                os.system(f"taskkill /F /PID {proc.pid}")  # 强制终止进程
        except psutil.NoSuchProcess:
            pass

def open_multiple_roblox():
    """ 打开多个 Roblox 实例 """
    roblox_path = r"C:\Users\你的用户名\AppData\Local\Roblox\Versions\版本号\RobloxPlayerBeta.exe"
    subprocess.Popen(roblox_path)  # 启动 Roblox
    time.sleep(2)  # 等待 2 秒，确保启动成功
    subprocess.Popen(roblox_path)  # 再次启动第二个 Roblox

if __name__ == "__main__":
    kill_roblox_mutex()  # 杀掉原有的 Roblox 锁
    open_multiple_roblox()  # 打开多个实例
- 👋 Hi, I’m @hao1hao0
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!---
hao1hao0/hao1hao0 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
