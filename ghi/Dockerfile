FROM ruby:alpine3.11

RUN gem install ghi -v 1.2.0 && apk add -U git ncurses less

ENTRYPOINT ["ghi"]
