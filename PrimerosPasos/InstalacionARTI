# Step 1: Pull the ARTI Docker image (download it locally from Docker Hub)
docker pull rmartinezmaple/arti_lidera:latest

# Step 2: Run a new container, give it a name in arti_name_of_container, mount a local folder to /workspace, and set entrypoint to bash

docker run -it --name arti_name_of_container -v /local/path:/workspace --entrypoint bash rmartinezmaple/arti_lidera:latest

# EXAMPLE: Run container named "arti_dev" mounting the folder /home/rafael/proyectos into /workspace

docker run -it --name arti_dev -v /home/rafael/proyectos:/workspace --entrypoint bash rmartinezmaple/arti_lidera:latest


########### Simulation of a  monocromatic flux 


# Step 3: Navigate to the ARTI simulation directory and run "rain.pl" with parameters cd /opt/arti/sim and in the folder do:

./rain.pl -r ../../corsika/run/ -v 78010 -h QGSIII -f fluka -s bga -m 1E5 -p 1 -q 0

# Step 4: Inside CORSIKA run folder, decompress all DAT files, analyze them with lagocrkread + analysis, and clean up cd /opt/corsika/run/nameoffoldermono

for i in DAT??????.bz2; do j=$(echo $i | sed -e 's/.bz2//'); u=$(echo $j | sed -e 's/DAT//'); bzip2 -d -k $i; echo $j | ../../../arti/analysis/lagocrkread | ../../../arti/analysis/analysis -p -v $u; rm $j; done

# Step 4: Decompress de file of secondary

bzip2 -d #####.sec.bz2


######################## EAS simulation ###############################

# Step 5: Run "do_sims.sh" to start simulations with specified parameters (workdir, project name, version, hadronic models, user, threads, site)
./do_sims.sh -w ../../corsika/run/ -p pruebacampinas -v 78010 -h QGSIII -f fluka -u username -t 15 -s bga

# Step 6: Execute all generated .sh files; you can run them manually or use runner.sh to automate execution
./runner.sh &> Cache &

# Note: runner.sh must be configured according to your CPU cores. On clusters, use more aggressive settings as it runs jobs in groups and waits for completion.

# Script: Loop over all compressed .lst files, print filename and last line of each (quick check of simulation results)
for file in DAT*.lst.bz2; do echo -n "$file: "; bzcat "$file" | tail -n 1; done

#Run again de step 8:

for i in DAT??????.bz2; do j=$(echo $i | sed -e 's/.bz2//'); u=$(echo $j | sed -e 's/DAT//'); bzip2 -d -k $i; echo $j | ../../../arti/analysis/lagocrkread | ../../../arti/analysis/analysis -p -v $u; rm $j; done


# Command: Decompress secondary particle files and analyze them with "showers" tool

bzcat *sec.bz2 | ../../../arti/analysis/showers -a 10 -d 10 -c 956. -n 1 1 -v salida
