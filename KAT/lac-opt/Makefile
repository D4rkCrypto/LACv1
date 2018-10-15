objects = ake.o ke.o kem.o encrypt.o ecc.o bch.o bin-lwe.o rand.o rng.o
mainobjects = PQCgenKAT_encrypt.o PQCgenKAT_kem.o PQCgenKAT_ke.o PQCgenKAT_ake.o
cflags = -O3 -Wall -DNDEBUG

all: katencrypt katkem katke katake

katencrypt : PQCgenKAT_encrypt.o $(objects)
	gcc -o katencrypt PQCgenKAT_encrypt.o $(objects) -lcrypto  

katkem : PQCgenKAT_kem.o $(objects)
	gcc -o katkem PQCgenKAT_kem.o $(objects) -lcrypto  

katke : PQCgenKAT_ke.o $(objects)
	gcc -o katke PQCgenKAT_ke.o $(objects) -lcrypto  

katake : PQCgenKAT_ake.o $(objects)
	gcc -o katake PQCgenKAT_ake.o $(objects) -lcrypto  

PQCgenKAT_encrypt.o: PQCgenKAT_encrypt.c api.h rng.h
	gcc -c PQCgenKAT_encrypt.c $(cflags)

PQCgenKAT_kem.o: PQCgenKAT_kem.c api.h rng.h
	gcc -c PQCgenKAT_kem.c $(cflags)

PQCgenKAT_ke.o: PQCgenKAT_ke.c api.h rng.h
	gcc -c PQCgenKAT_ke.c $(cflags)

PQCgenKAT_ake.o: PQCgenKAT_ake.c api.h rng.h
	gcc -c PQCgenKAT_ake.c $(cflags)

ake.o: ake.c api.h rand.h lac_param.h
	gcc -c ake.c $(cflags)

ke.o: ke.c api.h rand.h lac_param.h
	gcc -c ke.c $(cflags)

kem.o: kem.c api.h rand.h ecc.h bin-lwe.h lac_param.h
	gcc -c kem.c $(cflags)

encrypt.o: encrypt.c api.h rand.h ecc.h bin-lwe.h lac_param.h 
	gcc -c encrypt.c $(cflags)

ecc.o: ecc.c bch.h ecc.h lac_param.h 
	gcc -c ecc.c $(cflags)

bch.o: bch.c bch.h 
	gcc -c bch.c $(cflags)

bin-lwe.o: bin-lwe.c lac_param.h rand.h bin-lwe.h 
	gcc -c bin-lwe.c $(cflags)

rand.o: rand.c lac_param.h rand.h
	gcc -c rand.c $(cflags) 

rng.o: rng.c rng.h
	gcc -c rng.c $(cflags) 

clean:
	rm -f katencrypt katencrypt.exemak katkem katkem.exemak katke katke.exemak katake katake.exemak $(mainobjects) $(objects)


          
