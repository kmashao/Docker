# FROM ruby:latest

# RUN apt-get update -y && apt-get install -y build-essential yarn nodejs sqlite3
# RUN apt-get upgrade -y yarn
# ONBUILD RUN /bin/bash -l -c "gem install  rails"
# #ONBUILD WORKDIR /opt
# ONBUILD COPY hello_app /opt
# #ONBUILD RUN mkdir /opt/app
# ONBUILD EXPOSE 3000
# #ONBUILD RUN rails new hello_app
# ONBUILD WORKDIR /opt/
# ONBUILD RUN bundle update
# ONBUILD RUN bundle install
# ONBUILD RUN rails db:migrate
# ONBUILD RUN rails db:seed

  
FROM ruby:latest
RUN apt-get update -y && apt-get upgrade -y
RUN apt-get install nodejs -y
RUN apt-get install yarn -y
RUN apt-get upgrade yarn -y
RUN gem install bundler
RUN /bin/bash -l -c  "gem install rails"
WORKDIR /opt
COPY hello_world /opt/
EXPOSE 3000
WORKDIR /opt/hello_world
RUN bundle update 
RUN bundle install
RUN rails db:create
RUN rake db:migrate