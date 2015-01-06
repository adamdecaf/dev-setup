IMAGE_NAME = "adamdecaf/dev-setup-base"
EMAIL_ADDRESS = "adam@ashannon.us"

desc "build base image"
task :build do
  if !File.exists?("base/configs/ssh") or File.zero?("base/configs/ssh")
    sh "ssh-keygen -f ./base/configs/ssh -t rsa -C #{EMAIL_ADDRESS}"
  end

  sh "docker build -t #{IMAGE_NAME} base/"
end

task :run do
  sh "docker run -it #{IMAGE_NAME}"
end

task :default => [:build]
