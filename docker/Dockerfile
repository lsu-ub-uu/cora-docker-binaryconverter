FROM  fedora:39

RUN dnf install ImageMagick -y
RUN dnf install java-17-openjdk -y

ARG workdir=/binaryConverter

RUN mkdir -p /tmp/sharedArchiveReadable/systemOne

WORKDIR ${workdir}

COPY /*.jar ${workdir}/
COPY /*.properties ${workdir}/properties/

CMD java -cp "properties/:/binaryConverter/*" \
se.uu.ub.cora.binaryconverter.BinaryConverter \
${coraBaseUrl} ${apptokenVerifierUrl} ${userId} ${appToken} \
${rabbitMqHostName} ${rabbitMqPort} ${rabbitMqVirtualHost} ${rabbitMqQueueName} \
${fedoraOcflHome} ${fileStorageBasePath}