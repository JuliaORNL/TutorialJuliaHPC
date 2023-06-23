```console
kol@leconte:~$ git clone https://github.com/JuliaORNL/GrayScott.jl.git
kol@leconte:~$ wget https://github.com/JuliaORNL/TutorialJuliaHPC/raw/main/docs/applications/GrayScott/run-leconte.zip
kol@leconte:~$ unzip run-leconte.zip && rm run-leconte.zip && cd run
kol@leconte:~/run$ chmod +x config_leconte.sh job_leconte.sh
kol@leconte:~/run$ source config_leconte.sh
kol@leconte:~/run$ # read job script documentation
kol@leconte:~/run$ cat job_leconte.sh
kol@leconte:~/run$ cp $GS_DIR/examples/settings-files.json 001
kol@leconte:~/run$ ./job_leconte.sh 001
```
