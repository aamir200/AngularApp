FROM nginx:stable
RUN rm /etc/nginx/conf.d/default.conf
RUN echo "server {\n\
        root /app;\n\
\n\
        location /healtz {\n\
            if (\$request_method = 'OPTIONS') {\n\
                add_header 'Access-Control-Allow-Origin' '*';\n\
                add_header 'Access-Control-Allow-Methods' 'GET, OPTIONS';\n\
                add_header 'Access-Control-Allow-Headers' '*';\n\
                add_header 'Access-Control-Max-Age' 1728000;\n\
                add_header 'Content-Type' 'text/plain; charset=utf-8';\n\
                add_header 'Content-Length' 0;\n\
                return 204;\n\
             }\n\
            if (\$request_method != 'GET') {\n\
                return 404;\n\
            }\n\
            add_header 'Access-Control-Allow-Origin' '*';\n\
            add_header 'Access-Control-Allow-Methods' 'GET, OPTIONS';\n\
            add_header 'Access-Control-Allow-Headers' '*';\n\
            try_files \$uri \$uri.json /healtz.json;\n\
        }\n\
\n\
        location /readiness {\n\
            if (\$request_method = 'OPTIONS') {\n\
                add_header 'Access-Control-Allow-Origin' '*';\n\
                add_header 'Access-Control-Allow-Methods' 'GET, OPTIONS';\n\
                add_header 'Access-Control-Allow-Headers' '*';\n\
                add_header 'Access-Control-Max-Age' 1728000;\n\
                add_header 'Content-Type' 'text/plain; charset=utf-8';\n\
                add_header 'Content-Length' 0;\n\
                return 204;\n\
             }\n\
            if (\$request_method != 'GET') {\n\
                return 404;\n\
            }\n\
            add_header 'Access-Control-Allow-Origin' '*';\n\
            add_header 'Access-Control-Allow-Methods' 'GET, OPTIONS';\n\
            add_header 'Access-Control-Allow-Headers' '*';\n\
            try_files \$uri \$uri.json /healtz.json;\n\
        }\n\
\n\
        location / {\n\
                try_files \$uri \$uri/ /index.html;\n\
        }\n\
}" > /etc/nginx/conf.d/ng-apps.conf
COPY dist/ /app/