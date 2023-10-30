FROM  fedora:39

RUN dnf install ImageMagick -y
RUN dnf install java-17-openjdk -y

ARG workdir=/binaryConverter

WORKDIR ${workdir}

COPY /*.jar ${workdir}/


#CMD java -classpath properties/:classicfedorasynchronizer.jar \ 
#se.uu.ub.cora.classicfedorasynchronizer.messaging.MessengerListenerStarter \
#${messaginghostname} ${messagingport} ${messagingroutingKey} ${messagingusername} \
#${messagingpassword} ${databaseurl} ${databaseuser} ${databasepassword} \
#${fedorabaseUrl} ${coraapptokenVerifierUrl} ${corabaseUrl} ${corauserId} ${coraapptoken}