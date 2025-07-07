connect to bandit15
then we have to use a ssl/tls connect to connect to bandit16 and retrieve the password though port 30001 and ip 127.0.0.1

so we run 'openssl s_client -connect 127.0.0.1:30001' now I only knew that I needed to use openssl s_client together but I didn't see anything written about -connect option in neither manual pages of openssl and s_client

so after we run the command above we have to enter the password of bandit15 "8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo" and we will get the password of bandit16