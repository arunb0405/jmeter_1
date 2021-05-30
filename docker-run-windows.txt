# Docker Windows Readme file.
# Cloned an existing Git Repo & docker image for this.

PS C:\Tools\blazeDemo> git clone https://github.com/swethapn/blazeDemo
Cloning into 'blazeDemo'...
remote: Enumerating objects: 27, done.
remote: Counting objects: 100% (27/27), done.
remote: Compressing objects: 100% (21/21), done.
remote: Total 27 (delta 7), reused 21 (delta 4), pack-reused 0R
Receiving objects: 100% (27/27), 576.74 KiB | 3.05 MiB/s, done.
Resolving deltas: 100% (7/7), done.

PS C:\Tools\blazeDemo> cd .\blazeDemo\

PS C:\Tools\blazeDemo\blazeDemo> docker pull swethapn14/repo_perf:JmeterLatest
JmeterLatest: Pulling from swethapn14/repo_perf
9123ac7c32f7: Pull complete
960cb2b71965: Pull complete
59a32350de21: Pull complete
Digest: sha256:cf5a835e5926802be00de969eeecc2313ffd32d11e5d3407d72055465254b964
Status: Downloaded newer image for swethapn14/repo_perf:JmeterLatest
docker.io/swethapn14/repo_perf:JmeterLatest

In CI, create the below folder structure and place the .jmx file there.

C:\jmeter-base\TestBlazedemo

#Run the below docker command from Poweshell

docker run -v C:/jmeter-base:/workspace swethapn14/repo_perf:JmeterLatest -n -t /workspace/TestBlazedemo/GetTopResultsApi.jmx -l /workspace/logs/GetTopResultsApi_10Vu.jtl -e -o /workspace/html

The index.html is created under html folder that shows the TPS of 1.