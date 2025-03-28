ARG version

FROM almalinux:${version:-9}
ENV course="Devops"\
    author="Ganesh"\
    duration="120 days"

# here is user1 is default value 
ARG username=some_user
ENV username=$username
RUN echo "Hello user: ${username, image version:${version}}" > hello.txt
CMD ["sleep", "200"]


