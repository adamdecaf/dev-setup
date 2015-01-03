IMAGE_NAME = "adamdecaf/dev-setup-base"

desc "clean_if_exists"
task :clean_if_exists do
  # sh "docker rmi #{IMAGE_NAME}"
end

task :build do
  begin
    sh "tar cf docker/configs.tar configs/*"
    sh "mkdir docker/bin/ && cp bin/* docker/bin/"
    sh "docker build -t #{IMAGE_NAME} docker/"
  ensure
    sh "rm docker/configs.tar"
    sh "rm -rf docker/bin/"
  end
end

task :run do
  sh "docker run -it #{IMAGE_NAME}"
end

task :default => [:clean_if_exists, :build]
