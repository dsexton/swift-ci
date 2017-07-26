# frozen_string_literal: true
desc 'Builds latest image'
task :build do
  Rake::Task['build:latest'].invoke
end

namespace :build do
  desc 'Builds all images'
  task :all do
    Rake::Task['build:latest'].invoke
  end

  desc 'Builds latest image'
  task :latest do
    sh 'docker build -t dsexton/swift-ci:latest --pull .'
  end
end

desc 'Pushes latest image'
task :push do
  Rake::Task['push:latest'].invoke
end

namespace :push do
  desc 'Pushes all images'
  task :all do
    Rake::Task['push:latest'].invoke
  end

  desc 'Pushes latest image to the registry'
  task :latest do
    sh 'docker push dsexton/swift-ci:latest'
  end
end

desc 'Builds & pushes all docker images'
task :deploy do
  Rake::Task['deploy:latest'].invoke
end

namespace :deploy do
  desc 'Builds & pushes all images'
  task :all do
    Rake::Task['deploy:latest'].invoke
  end

  desc 'Builds & pushes latest image to the registry'
  task :latest do
    Rake::Task['build:latest'].invoke
    Rake::Task['push:latest'].invoke
  end
end
