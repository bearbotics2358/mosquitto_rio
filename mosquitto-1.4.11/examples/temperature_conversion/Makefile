CFLAGS=-Wall -ggdb -I../../lib -I../../lib/cpp
LDFLAGS=-L../../lib ../../lib/cpp/libmosquittopp.so.1 ../../lib/libmosquitto.so.1

.PHONY: all clean

all : mqtt_temperature_conversion

mqtt_temperature_conversion : main.o temperature_conversion.o
	${CROSS_COMPILE}${CXX} $^ -o $@ ${LDFLAGS}

main.o : main.cpp
	${CROSS_COMPILE}${CXX} -c $^ -o $@ ${CFLAGS}

temperature_conversion.o : temperature_conversion.cpp
	${CROSS_COMPILE}${CXX} -c $^ -o $@ ${CFLAGS}

clean : 
	-rm -f *.o mqtt_temperature_conversion
