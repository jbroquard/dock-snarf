# 2019-03-10 (cc) <paul4hough@gmail.com>

FROM nginx
COPY nginx.conf /etc/nginx/nginx.conf

EXPOSE 80

STOPSIGNAL SIGTERM

CMD ["nginx", "-g", "daemon off;"]
