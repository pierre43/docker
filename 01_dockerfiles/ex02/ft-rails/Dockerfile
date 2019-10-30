FROM ruby

RUN apt-get update -y && apt-get upgrade -y && gem install rails && apt-get install nodejs -y

ONBUILD ADD . /opt/app
ONBUILD WORKDIR /opt/app

ONBUILD RUN bundle install && rails db:migrate && rails db:seed
