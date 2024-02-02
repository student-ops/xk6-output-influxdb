mkdir my_k6_path

docker run --rm -it -u "$(id -u):$(id -g)" -v "${PWD}:/xk6" grafana/xk6 build v0.49.0 --with github.com/pmalhaire/xk6-mqtt@v0.40.0

./k6 run --vus 50 --duration 10s samples/
