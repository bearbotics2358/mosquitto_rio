CFLAGS=-Wall -ggdb
LDFLAGS=../../lib/libmosquitto.so.1 -lmysqlclient

.PHONY: all clean

all : mosquitto_mysql_log

mosquitto_mysql_log : mysql_log.o
	${CROSS_COMPILE}${CC} $^ -o $@ ${LDFLAGS}

mysql_log.o : mysql_log.c
	${CROSS_COMPILE}${CC} -c $^ -o $@ ${CFLAGS} -I../../lib

clean : 
	-rm -f *.o mosquitto_mysql_log
