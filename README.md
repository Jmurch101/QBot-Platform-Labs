# QBot Platform — Python Labs

Lean subset of Quanser Academic Resources for running **physical QBot Platform** Python scripts.

## Layout

```
0_libraries/python/          # pal + hal (QBot Platform APIs)
2_quick_start_guides/.../python/
6_teaching/3_Robotics/
  sp0_play/play_qbot/hardware/python/          # play.py
  sp1_task_automation/
    l1_forward_kinematics/hardware/python/     # for_kin.py
    l2_inverse_kinematics/hardware/python/     # inv_kin.py
    l3_line_following/hardware/python/         # line_following.py
    l4_object_detection/hardware/python/       # obstacle_detection.py
```

Each lab folder also includes the physical driver
(`qbot_platform_driver_physical.rt-linux_qbot_platform`), observer helper, and PDFs.

## Setup on the QBot

Point Python at the libraries (already set up on your bots if you followed Quanser setup):

```bash
export PYTHONPATH="/path/to/Quanser_Academic_Resources/0_libraries/python:$PYTHONPATH"
```

Run a lab from its `hardware/python` directory so the local `.rt-linux_qbot_platform` driver is found, e.g.:

```bash
cd 6_teaching/3_Robotics/sp0_play/play_qbot/hardware/python
python3 play.py
```

Scripts start the Quarc driver via `quarc_run` against `localhost`, then talk to cameras/lidar/gamepad through `pal` / `hal`.

## Pushing scripts to QBots

Copy (or rsync/scp) this repo onto each QBot, then run the lab scripts above. Keep relative paths so each lab’s driver binary stays next to its `.py` file.
