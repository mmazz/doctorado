# Instalar y usar docker

sudo docker buildx build --network=host --build-context project=$HOME/documents/doctorado/docker-gem5 -t ubuntu .
sudo docker run -u 1000:$GID --volume ~/documents/doctorado/gem5:/gem5 --name gem5 -u root --rm -it ubuntu
Si saco el -u root, tengo el problema de no lograr tener password para el usario.


# Compile

cd gem5/tests/test-progs/
gcc -ggdb3 -O3 -D__DEBUG -c ../pthread.c -o ../pthread.o
g++-4.8 -static -std=c++11 -lpthread -Wl,--no-whole-archive test.cpp -o test

# Things to try


git clone --depth 1 --branch v19.0.0.0 https://gem5.googlesource.com/public/gem5
python3 `which scons` build/X86/gem5.opt -j9
