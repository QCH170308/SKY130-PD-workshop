# SKY130-PD-workshop

# Day1-Inception of open-source EDA, OpenLANE and Sky130 PDK

![image](https://user-images.githubusercontent.com/65656088/183255373-b4418d87-18b5-4f66-a72f-adbfbc1c7e0f.png)

Let's first look into "pdks", this folder contains all informations related to the PDK (Process Design Kit). The PDK which is used in this workshop is a open source PDK named Skywater 130nm. 

![image](https://user-images.githubusercontent.com/65656088/183255637-e3f7b3b0-8b13-456e-903d-653468be5730.png)

The first folder "skywater-pdk" has all the pdk related files. 

![image](https://user-images.githubusercontent.com/65656088/183256204-a7328914-6c34-4df1-adf9-a3d537773b4c.png)

![image](https://user-images.githubusercontent.com/65656088/183256251-01b4cc89-60fe-4e02-879d-789c6e5420fa.png)

![image](https://user-images.githubusercontent.com/65656088/183256276-c3af617b-5c7f-40c6-a685-2e6efdd19dfe.png)

![image](https://user-images.githubusercontent.com/65656088/183256337-e9a4ebd5-9fa0-421a-b6e5-319f2b191e48.png)

![image](https://user-images.githubusercontent.com/65656088/183256666-541d0088-a081-432e-a3b8-aa7477f3d76a.png)

![image](https://user-images.githubusercontent.com/65656088/183256689-2f7bb32a-1298-4049-bc6a-f45a9bed91dd.png)

![image](https://user-images.githubusercontent.com/65656088/183256825-14a5f2bb-354c-48eb-b556-73dd219392b8.png)

![image](https://user-images.githubusercontent.com/65656088/183256887-f4a896ad-466d-43e1-a589-20a24f0c83d0.png)

![image](https://user-images.githubusercontent.com/65656088/183256920-21c5ec35-78c9-4b37-9917-b2fe1bd89160.png)

![image](https://user-images.githubusercontent.com/65656088/183257392-d2aae2cf-9e82-49bb-b07f-7180cd2feb85.png)

The Flop ratio from 1-yosys_4.stat.rpt is 1613/14876=0.1084 (no. of dfxtp (d filpflop) / no. of cells)

The buffer (buf1) ratio is 1656/14876=0.1113 (no. of buf_1 / no. of cells)

# Day2-Good floorplan vs bad floorplan and introduction to library cells

Go to path:
/home/quanch/Desktop/work/tools/openlane_working_dir/openlane/configuration

Then open README.md

![image](https://user-images.githubusercontent.com/65656088/183280685-60a7f5c8-1b4c-45cb-af86-fea81fe3f31e.png)

![image](https://user-images.githubusercontent.com/65656088/183280824-3dc5a409-47d4-4b1e-aa92-7e56471f216e.png)

Then open floorplan.tcl in the same folder

![image](https://user-images.githubusercontent.com/65656088/183280913-044e7bb8-2d86-49d7-8ff4-fd68af426876.png)

Under the path:

/home/quanch/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a

![image](https://user-images.githubusercontent.com/65656088/183280984-173c455c-2c74-463f-a753-19ac168f3e26.png)

There are two settings: sky130A_sky130_fd_sc_hd_config.tcl and config.tcl

The priority of these settings are: sky130A_sky130_fd_sc_hd_config.tcl > config.tcl > floorplan.tcl

Then run "run_floorplan" in OpenLANE

![image](https://user-images.githubusercontent.com/65656088/183281165-97759155-a691-439a-9488-6a7c8121064c.png)

Go to the path:

/home/quanch/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/06-08_16-05/logs/floorplan

Then open 4-ioPlacer.log

![image](https://user-images.githubusercontent.com/65656088/183281332-294e15f6-ec77-4156-9f8d-edbb85aca139.png)

![image](https://user-images.githubusercontent.com/65656088/183281569-1ee5c92b-76b1-423e-9042-eff3cec037a5.png)

Go to the path:

/home/quanch/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/06-08_16-05

And open config.tcl

![image](https://user-images.githubusercontent.com/65656088/183281898-410a8ee0-4e22-4985-8110-6208cfae6125.png)

In the path:

/home/quanch/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a

The file: sky130A_sky130_fd_sc_hd_config.tcl

![image](https://user-images.githubusercontent.com/65656088/183281930-9aea8187-657b-4824-ba24-d833cae14439.png)

Go to the path:

/home/quanch/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/06-08_16-05/results/floorplan

Open picorv32a.floorplan.def

![image](https://user-images.githubusercontent.com/65656088/183282040-d6e80494-a9f0-4425-b6e1-cde88730a5cb.png)

Then under the same folder run command:

magic -T /home/quanch/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.lef def read picorv32a.floorplan.def &

![image](https://user-images.githubusercontent.com/65656088/183282234-33bc0030-7ae6-4d82-b16e-0c7c9765f97c.png)

