FROM rockstorm/jekyll:latest
RUN gem update --system 3.4.20
# Copy Gemfile because sometimes the bundle version is different
# install the required bundler and install all the dependencies
COPY Gemfile* ./
RUN gem install bundler -v 2.4.20 && bundle install
ENTRYPOINT [ "jekyll" ]
CMD [ "build" ]