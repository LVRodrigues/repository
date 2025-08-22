FROM ubuntu:focal

RUN apt-get update && apt-get install -y locales git curl && \
    rm -rf /var/lib/apt/lists/* && localedef -i en_US -c -f UTF-8 -A /usr/share/locale/locale.alias en_US.UTF-8 
ENV LANG en_US.utf8

RUN curl -sSL https://get.rvm.io | bash -s stable 
ENV PATH /usr/local/rvm/bin:/usr/local/rvm/gems/ruby-2.7.2/bin:/usr/local/rvm/gems/ruby-2.7.2@global/bin:/usr/local/rvm/rubies/ruby-2.7.2/bin:$PATH
ENV GEM_HOME /usr/local/rvm/gems/ruby-2.7.2
ENV GEM_PATH /usr/local/rvm/gems/ruby-2.7.2:/usr/local/rvm/gems/ruby-2.7.2@global
ENV MY_RUBY_HOME /usr/local/rvm/rubies/ruby-2.7.2
ENV IRBRC /usr/local/rvm/rubies/ruby-2.7.2/.irbrc
ENV RUBY_VERSION ruby-2.7.2>
RUN rvm --default install ruby-2.7 && \
    gem update --system 3.4.18 && \
    gem install bundler -v 2.4.18 && \
    gem install jekyll -v 3.10.0
