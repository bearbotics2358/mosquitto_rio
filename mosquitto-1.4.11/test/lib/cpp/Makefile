.PHONY: all test 01 02 03 04 08 09 clean reallyclean

CFLAGS=-I../../../lib -I../../../lib/cpp -DDEBUG -Werror
LIBS=../../../lib/libmosquitto.so.1 ../../../lib/cpp/libmosquittopp.so.1

all : 01 02 03 04 08 09

01-con-discon-success.test : 01-con-discon-success.cpp
	${CROSS_COMPILE}${CXX} $< -o $@ $(CFLAGS) $(LIBS)

01-will-set.test : 01-will-set.cpp
	${CROSS_COMPILE}${CXX} $< -o $@ $(CFLAGS) $(LIBS)

01-unpwd-set.test : 01-unpwd-set.cpp
	${CROSS_COMPILE}${CXX} $< -o $@ $(CFLAGS) $(LIBS)

01-will-unpwd-set.test : 01-will-unpwd-set.cpp
	${CROSS_COMPILE}${CXX} $< -o $@ $(CFLAGS) $(LIBS)

01-no-clean-session.test : 01-no-clean-session.cpp
	${CROSS_COMPILE}${CXX} $< -o $@ $(CFLAGS) $(LIBS)

01-keepalive-pingreq.test : 01-keepalive-pingreq.cpp
	${CROSS_COMPILE}${CXX} $< -o $@ $(CFLAGS) $(LIBS)

02-subscribe-qos0.test : 02-subscribe-qos0.cpp
	${CROSS_COMPILE}${CXX} $< -o $@ $(CFLAGS) $(LIBS)

02-subscribe-qos1.test : 02-subscribe-qos1.cpp
	${CROSS_COMPILE}${CXX} $< -o $@ $(CFLAGS) $(LIBS)

02-subscribe-qos2.test : 02-subscribe-qos2.cpp
	${CROSS_COMPILE}${CXX} $< -o $@ $(CFLAGS) $(LIBS)

02-unsubscribe.test : 02-unsubscribe.cpp
	${CROSS_COMPILE}${CXX} $< -o $@ $(CFLAGS) $(LIBS)

03-publish-qos0.test : 03-publish-qos0.cpp
	${CROSS_COMPILE}${CXX} $< -o $@ $(CFLAGS) $(LIBS)

03-publish-qos0-no-payload.test : 03-publish-qos0-no-payload.cpp
	${CROSS_COMPILE}${CXX} $< -o $@ $(CFLAGS) $(LIBS)

03-publish-c2b-qos1-timeout.test : 03-publish-c2b-qos1-timeout.cpp
	${CROSS_COMPILE}${CXX} $< -o $@ $(CFLAGS) $(LIBS)

03-publish-c2b-qos1-disconnect.test : 03-publish-c2b-qos1-disconnect.cpp
	${CROSS_COMPILE}${CXX} $< -o $@ $(CFLAGS) $(LIBS)

03-publish-c2b-qos2.test : 03-publish-c2b-qos2.cpp
	${CROSS_COMPILE}${CXX} $< -o $@ $(CFLAGS) $(LIBS)

03-publish-c2b-qos2-disconnect.test : 03-publish-c2b-qos2-disconnect.cpp
	${CROSS_COMPILE}${CXX} $< -o $@ $(CFLAGS) $(LIBS)

03-publish-c2b-qos2-timeout.test : 03-publish-c2b-qos2-timeout.cpp
	${CROSS_COMPILE}${CXX} $< -o $@ $(CFLAGS) $(LIBS)

03-publish-b2c-qos1.test : 03-publish-b2c-qos1.cpp
	${CROSS_COMPILE}${CXX} $< -o $@ $(CFLAGS) $(LIBS)

03-publish-b2c-qos2.test : 03-publish-b2c-qos2.cpp
	${CROSS_COMPILE}${CXX} $< -o $@ $(CFLAGS) $(LIBS)

04-retain-qos0.test : 04-retain-qos0.cpp
	${CROSS_COMPILE}${CXX} $< -o $@ $(CFLAGS) $(LIBS)

08-ssl-connect-no-auth.test : 08-ssl-connect-no-auth.cpp
	${CROSS_COMPILE}${CXX} $< -o $@ $(CFLAGS) $(LIBS)

08-ssl-connect-cert-auth.test : 08-ssl-connect-cert-auth.cpp
	${CROSS_COMPILE}${CXX} $< -o $@ $(CFLAGS) $(LIBS)

08-ssl-connect-cert-auth-enc.test : 08-ssl-connect-cert-auth-enc.cpp
	${CROSS_COMPILE}${CXX} $< -o $@ $(CFLAGS) $(LIBS)

08-ssl-bad-cacert.test : 08-ssl-bad-cacert.cpp
	${CROSS_COMPILE}${CXX} $< -o $@ $(CFLAGS) $(LIBS)

08-ssl-fake-cacert.test : 08-ssl-fake-cacert.cpp
	${CROSS_COMPILE}${CXX} $< -o $@ $(CFLAGS) $(LIBS)

09-util-topic-matching.test : 09-util-topic-matching.cpp
	${CROSS_COMPILE}${CXX} $< -o $@ $(CFLAGS) $(LIBS)

09-util-topic-tokenise.test : 09-util-topic-tokenise.cpp
	${CROSS_COMPILE}${CXX} $< -o $@ $(CFLAGS) $(LIBS)

01 : 01-con-discon-success.test 01-will-set.test 01-unpwd-set.test 01-will-unpwd-set.test 01-no-clean-session.test 01-keepalive-pingreq.test

02 : 02-subscribe-qos0.test 02-subscribe-qos1.test 02-subscribe-qos2.test 02-unsubscribe.test

03 : 03-publish-qos0.test 03-publish-qos0-no-payload.test 03-publish-c2b-qos1-timeout.test 03-publish-c2b-qos1-disconnect.test 03-publish-c2b-qos2.test 03-publish-c2b-qos2-timeout.test 03-publish-c2b-qos2-disconnect.test 03-publish-b2c-qos1.test 03-publish-b2c-qos2.test

04 : 04-retain-qos0.test

08 : 08-ssl-connect-no-auth.test 08-ssl-connect-cert-auth.test 08-ssl-connect-cert-auth-enc.test 08-ssl-bad-cacert.test 08-ssl-fake-cacert.test

09 : 09-util-topic-matching.test 09-util-topic-tokenise.test

reallyclean : clean
	-rm -f *.orig

clean :
	rm -f *.test
