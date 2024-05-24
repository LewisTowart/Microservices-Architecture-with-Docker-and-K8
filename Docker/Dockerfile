# this dockerfile is to build an image/microservice to host static webpage


# which base image to use

FROM nginx

# who is building it
LABEL MAINTAINER=LTOWART@SPARTAGLOBAL.COM

# copy the index.html from localhost to /usr/share/nginx/html/
COPY index.html /usr/share/nginx/html/

# which ports to expose/enable
EXPOSE 80

# launch the server / nginx offical command using CMD
CMD ["nginx", "-g", "daemon off;"]

# ensure to create this Dockerfile where the index.html is located
