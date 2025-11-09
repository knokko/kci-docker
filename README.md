To build version 0.1.6 for MC 1.21:
```
docker build --file ./mc1.21/Dockerfile --tag 0.1.6-mc1.21 .
```

To publish version 0.1.6 for MC 1.21:
```
docker login
docker tag 0.1.6-mc1.21 knokkogator/kci:0.1.6-mc1.21
docker push knokkogator/kci:0.1.6-mc1.21
```
