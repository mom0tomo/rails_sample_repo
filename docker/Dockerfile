FROM ruby:3.1.2

RUN mkdir /app
WORKDIR /app

COPY Gemfile /app/Gemfile
COPY Gemfile.lock /app/Gemfile.lock
RUN bundle install
COPY . /app

COPY ./docker/docker-entrypoint.sh /usr/bin/
RUN chmod +x /usr/bin/docker-entrypoint.sh
ENTRYPOINT ["/usr/bin/docker-entrypoint.sh"]
EXPOSE 3000
ENV TZ Asia/Tokyo

CMD ["rails", "server", "-b", "0.0.0.0"]
