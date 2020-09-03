# s2i build https://github.com/sgaoshang/s2i-python-container.git --context-dir=3.6/test/setup-test-app/ ubi8/python-36 python-sample-app --as-dockerfile Dockerfile
# podman build . -t quay.io/sgaoshang/python-sample-app
# podman push quay.io/sgaoshang/python-sample-app