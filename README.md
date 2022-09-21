# Learning multiprocessing etc for better usage of CPU Cores

## Requirements
python 3.10.**      // I have actual version 3.10.7
    python --version
pip3
    pip3 --version
install scipy.io.wavfile and numpy
    pip3 install scipy      // numpy will install too
## Other way how to install (pipenv)
Pipenv is like a venv, but simulates same environment on basic of creator OS
without defining os path or so due to another way how to write path in other systems

python 3.10.**      // I have actual version 3.10.7
    python --version
pip3
    pip3 --version
### Windows
pip3 install pipenv
pipenv -h           // shows help


### Global Interpreter Lock
AKA GIL
- parallel processing primitive, that helps threads 
 prevent themselves from accessing same data at same time
- prevent one thread to read or write data when other 
is writing too
- insured by my OS and hardware

## Threading
- non-cooperative pausing/interrupting
- good for IO bound
- good to do long-running ops w/o blocking
- good for GUI application where you want to run a long 
running calculation off the main thread to maintain 
responsiveness
- many says in future people wont use Threading 
for max utilization ou of CPU

## Pools
avoid managing processes myself use Pool when possible
from multiprocessing import Pool, Process
Its process pool
results = pool.imap_unordered(etl, filenames)
or less Cache memory but little slower
results = pool.map(etl, filenames)
### setup max processes
with Pool(processes=5) as pool:

### imap_unordered
returns results in processed time 
(faster is 3rdfile will write faster)
