*Install env*
(https://kripken.github.io/emscripten-site/docs/getting_started/Tutorial.html)
git clone https://github.com/juj/emsdk.git
git pull
./emsdk install latest
./emsdk activate latest
source ./emsdk_env.sh
echo $PATH
emcc -v

*Hello world*
mkdir helloWorld
cd helloWorld/
sublime .
<see hello_world.c>
emcc hello_world.c
node a.out.js
emcc hello_world.c -o hello.html
open hello.html

*Fibonacci*
mkdir fib
cd fib
touch fib.c
sublime .
<see fib.c>
emcc -O3 -s WASM=1 -s EXTRA_EXPORTED_RUNTIME_METHODS='["cwrap"]' fib.c
touch fib.html
open fib.html #fails, must be run in a websvr
emrun fib.html     



