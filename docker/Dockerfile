FROM fedora:41

RUN dnf clean all
RUN dnf install ImageMagick -y
RUN dnf install openjpeg2-tools -y
RUN dnf install java-23-openjdk -y

ARG workdir=/binaryConverter

RUN mkdir -p /tmp/sharedArchiveReadable/systemOne
RUN mkdir -p /tmp/sharedArchiveReadable/alvin
RUN mkdir -p /tmp/sharedArchiveReadable/diva

WORKDIR ${workdir}

COPY /*.jar ${workdir}/
COPY /*.properties ${workdir}/properties/

CMD java -cp "properties/:/binaryConverter/*" \
se.uu.ub.cora.binaryconverter.BinaryConverter \
${coraBaseUrl} ${apptokenVerifierUrl} ${loginId} ${appToken} \
${rabbitMqHostName} ${rabbitMqPort} ${rabbitMqVirtualHost} ${rabbitMqQueueName} \
${fedoraOcflHome} ${fileStorageBasePath}