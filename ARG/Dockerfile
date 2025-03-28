FROM almalinux:9
ENV course="Devops"\
    author="Ganesh"\
    duration="120 days"

# here is user1 is default value 
ARG ${username:-some_user}
RUN echo "Hello ${username}" > /tmp/arg.txt
CMD ["sleep", "200"]


