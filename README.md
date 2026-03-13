# uav-neo-installer
Template repository for native UAV Neo installation on local computer

---

## Installation

1. Clone the install repository into your computer (entry point)

```sh
git clone https://github.com/MITUavNeo/uav-neo-installer.git
```

2. Run the installer script

```sh
bash uav-neo-installer/drone-student/scripts/setup.sh
```

3. When prompted, select your operating system and class type.

```sh
Welcome to the UAV Neo Drone command-line installer for Windows, Mac, and Linux.
[1/3] Select your operating system: [windows, mac, linux]
1) windows
2) mac
3) linux
#? 1
Cloning into 'UAVNeo-Simulator'...
remote: Enumerating objects: 445, done.
remote: Counting objects: 100% (213/213), done.
remote: Compressing objects: 100% (39/39), done.
remote: Total 445 (delta 197), reused 174 (delta 174), pack-reused 232 (from 1)
Receiving objects: 100% (445/445), 82.54 MiB | 26.63 MiB/s, done.
Resolving deltas: 100% (293/293), done.
[2/3] Select your course curriculum: [oneshot]
1) oneshot
Cloning into 'uav-neo-library'...
remote: Enumerating objects: 32, done.
remote: Counting objects: 100% (32/32), done.
remote: Compressing objects: 100% (31/31), done.
remote: Total 32 (delta 3), reused 27 (delta 1), pack-reused 0 (from 0)
Receiving objects: 100% (32/32), 32.52 KiB | 16.26 MiB/s, done.
Resolving deltas: 100% (3/3), done.
Cloning into 'uav-neo-oneshot-labs'...
remote: Enumerating objects: 11, done.
remote: Counting objects: 100% (11/11), done.
remote: Compressing objects: 100% (9/9), done.
remote: Total 11 (delta 2), reused 7 (delta 2), pack-reused 0 (from 0)
Receiving objects: 100% (11/11), 18.60 KiB | 1002.00 KiB/s, done.
Resolving deltas: 100% (2/2), done.
[3/3] Installing all drone libraries and dependencies...
```

4. Enter your sudo password and wait for the installation to finish. Then, source your environment. You should see a `(drone-venv)` virtual environment be created.

```sh
source ~/.bashrc
```

<img width="860" height="21" alt="image" src="https://github.com/user-attachments/assets/9abc356c-51d8-49d3-be5c-ed9c6fde2ebb" />


5. Install pip dependencies.

```sh
pip install --upgrade pip
pip install -r uav-neo-installer/drone-student/scripts/requirements.txt
```

6. Test the custom `drone` command.

```sh
drone test
```

```sh
drone tool set up successfully!
  DRONE_ABSOLUTE_PATH: /home/chris/uav-neo-testing/uav-neo-installer/drone-student
  DRONE_IP: 127.0.0.1
  DRONE_TEAM: student
```

7. Open the simulator.

```sh
drone cd && cd ../../UAVNeo-Simulator

# Open file in file explorer
explorer.exe .    # Windows
open .            # Mac
nautilus .        # Linux

# Find the executable called UAVSim and open it.
UAVSim.exe
UAVSim.app
UAVSim.x86_64
```

8. In the terminal, run `demo.py` to check that the setup was successful.

```sh
drone cd

drone sim demo.py

# Hit the Enter key in the simulator.
# The "A" button (1 key on computer) prints a statement to the terminal (Sim -> Python check)
# The "B" button (2 key on computer) launches the drone, flies it forward and to the right, then lands the drone (Python <-> Sim check)
```

<img width="982" height="136" alt="image" src="https://github.com/user-attachments/assets/cab38681-e3b9-4453-a8d9-d8b3d4c546ce" />


<img width="947" height="529" alt="image" src="https://github.com/user-attachments/assets/b1fd92c9-529f-40ec-afd7-6b1e409ba55e" />
