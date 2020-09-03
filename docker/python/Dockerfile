FROM ubi8/python-36
LABEL "io.openshift.s2i.build.image"="ubi8/python-36" \
      "io.openshift.s2i.build.commit.author"="sgao <sgao@redhat.com>" \
      "io.openshift.s2i.build.commit.date"="Thu Sep 3 13:30:13 2020 +0800" \
      "io.openshift.s2i.build.commit.ref"="master" \
      "io.k8s.display-name"="python-sample-app" \
      "io.openshift.s2i.build.commit.id"="b290d4c94d05b86e43c5ed0be24da169ca005dc7" \
      "io.openshift.s2i.build.commit.message"="change web content" \
      "io.openshift.s2i.build.source-location"="https://github.com/sgaoshang/s2i-python-container.git" \
      "io.openshift.s2i.build.source-context-dir"="3.6/test/setup-test-app/"

USER root
# Copying in source code
COPY upload/src /tmp/src
# Change file ownership to the assemble user. Builder image must support chown command.
RUN chown -R 1001:0 /tmp/src
USER 1001
# Assemble script sourced from builder image based on user input or image metadata.
# If this file does not exist in the image, the build will fail.
RUN /usr/libexec/s2i/assemble
# Run script sourced from builder image based on user input or image metadata.
# If this file does not exist in the image, the build will fail.
CMD /usr/libexec/s2i/run