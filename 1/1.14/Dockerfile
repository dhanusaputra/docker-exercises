FROM ruby:3.0.0
RUN apt-get update && apt-get install -y git curl
RUN git clone https://github.com/docker-hy/rails-example-project.git
WORKDIR "/rails-example-project"
RUN curl -sL https://deb.nodesource.com/setup_10.x | bash
RUN apt install -y nodejs
RUN npm install -g yarn
RUN gem install bundler:2.2.11
RUN bundle install
RUN rails db:migrate RAILS_ENV=production
RUN rake assets:precompile
EXPOSE 3000
CMD ["rails", "s", "-e", "production"]
