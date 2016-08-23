FROM sysart/sensu-base
ENTRYPOINT ["/opt/sensu/embedded/bin/sensu-server"]
RUN apt-get -qq update && apt-get install -qq -y build-essential && apt-get -qq clean
CMD ["-c", "/etc/sensu/config.json", "-d", "/etc/sensu/config.d" ]
