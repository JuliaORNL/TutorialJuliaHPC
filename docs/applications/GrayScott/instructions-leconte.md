```console
kol@leconte:~$ git clone https://github.com/JuliaORNL/GrayScott.jl.git
kol@leconte:~$ wget https://github.com/JuliaORNL/TutorialJuliaHPC/raw/main/docs/applications/GrayScott/run-leconte.zip
kol@leconte:~$ unzip run-leconte.zip && rm run-leconte.zip && cd run001
kol@leconte:~/run001$ cp ../GrayScott.jl/examples/settings-files.json .
kol@leconte:~/run001$ chmod +x config_leconte.sh job_leconte.sh
kol@leconte:~/run001$ source config_leconte.sh
kol@leconte:~/run001$ ./job_leconte.sh
```
