FROM ruby:2.4.5-stretch

RUN apt-get update --fix-missing \
 && apt-get -y update \
 && apt-get install -y chromedriver \
                       imagemagick \
                       tzdata \
 && apt-get autoremove -y

COPY .gitignore /app/.gitignore
COPY Gemfile /app/Gemfile
COPY Gemfile.lock /app/Gemfile.lock
COPY fat_free_crm.gemspec /app/fat_free_crm.gemspec
COPY lib/fat_free_crm/version.rb /app/lib/fat_free_crm/version.rb
COPY vendor/gems /app/vendor/gems

WORKDIR /app

RUN bundle install --jobs=5

CMD ["/bin/bash"]
