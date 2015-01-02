IMAGE_NAME = "adamdecaf/dev-setup-base"

desc "clean_if_exists"
task :clean_if_exists do
  # sh "docker rmi #{IMAGE_NAME}"
end

task :build do
  sh "docker build -t #{IMAGE_NAME} docker/"
end

task :run do
  sh "docker run -it #{IMAGE_NAME}"
end

task :default => [:clean_if_exists, :build]
