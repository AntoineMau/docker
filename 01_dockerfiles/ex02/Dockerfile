FROM ruby as builder

EXPOSE 3000

WORKDIR /usr/src/app
RUN gem install bundler; \
	bundle install; \
	bundle update
COPY Gemfile Gemfile.lock ./

ENTRYPOINT 