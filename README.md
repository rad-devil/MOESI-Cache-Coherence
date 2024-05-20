# MOESI-Cache-Coherence
Implemented Cache Coherence MOESI CMP (multicore) Protocol in Gem5 using ruby memory system and the domain specific language SLICC
<img width="600" alt="Screenshot 2024-05-19 at 4 55 06 PM" src="https://github.com/rad-devil/MOESI-Cache-Coherence/assets/145730909/fe188e40-7a74-46b7-860f-1153fd780bc1">

These 8 base states were given. The task was to draw 8 other transient states between these states by looking at the transistion code blocks present in  'MOESI_CMP_directory-L1cache.sm' (L1 Cache directory file).
The updated diagram :
![image](https://github.com/rad-devil/MOESI-Cache-Coherence/assets/145730909/d21b7bae-eab0-4e1c-a4ff-907450f45a00)

Results:
Correct implementation was tested by running a benchmark test

The project involved modifying the 'MOESI_CMP_directory-L1cache.sm' file

Steps to Run the code
1. Setup Gem5 on VM on Ubuntu (Instructions can be find online)
2. Building Gem5 with the required protocol. Run Command:
   scons build/X86_MOESI/gem5.opt --default=X86 RUBY=True PROTOCOL=MOESI_CMP_directory
3. Unzip the "project4benchmarks.zip” and move the benchmark folder provided to the gem5 folder
4. Run the benchmark with the following command:
   ./build/X86_MOESI/gem5.opt -d [path to target directory]
./configs/example/se.py -n 2 --cpu-type=DerivO3CPU --ruby -c
./project4benchmarks/dijkstra -o ./project4benchmarks/input.dat
5. Create Patch File: diff -ruN gem5_clean/src/mem/ruby/protocol
gem5/src/mem/ruby/protocol > project4.patch
Note : This will generate project4.patch and the directory conf1 to verify that the results are correct.    
