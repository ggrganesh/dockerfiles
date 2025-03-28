FROM almalinux:9 
RUN dnf install nginx -y
RUN rm -rf /usr/share/nginx/html/index.html
# this excutes if any user uses as there base OS 
ONBUILD COPY index.html /usr/share/nginx/html/index.html
CMD ["nginx", "g", "demaon off;"]
