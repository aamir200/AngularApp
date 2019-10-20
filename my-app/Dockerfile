FROM nginx:stable
RUN rm /etc/nginx/conf.d/default.conf
COPY ng-apps.conf /etc/nginx/conf.d/ng-apps.conf
COPY dist/ /app/