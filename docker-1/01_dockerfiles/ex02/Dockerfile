FROM ruby

RUN apt-get update && apt-get upgrade -y
RUN apt-get install build-essential libffi-dev libssl-dev libreadline-dev zlib1g-dev libsqlite3-dev -y
RUN apt-get install nodejs -y
RUN gem install rails bundler

COPY app_ruby/ /opt/app
WORKDIR /opt/app

ONBUILD RUN bundle install
ONBUILD RUN rake db:migrate
ONBUILD RUN rake db:seed
