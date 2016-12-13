FROM centos/ruby-23-centos7:latest
USER root
RUN  yum install -y java-1.8.0-openjdk && yum clean all -y
COPY s2i/bin/ $STI_SCRIPTS_PATH
USER 1001
COPY gitconfig $HOME/.gitconfig
COPY Gemfile Gemfile.lock $HOME/
RUN source /opt/app-root/etc/scl_enable && \
    bundle install
CMD $STI_SCRIPTS_PATH/usage
