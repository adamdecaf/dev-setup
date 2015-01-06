EMAIL_ADDRESS = "adam@ashannon.us"

desc "build base image"
task :build_base do
  if !File.exists?("base/configs/ssh") or File.zero?("base/configs/ssh")
    sh "ssh-keygen -f ./base/configs/ssh -t rsa -C #{EMAIL_ADDRESS}"
  end

  sh "cd base && docker build -t adamdecaf/dev-setup-base ."
end

task :run_base do
  sh "docker run -it adamdecaf/dev-setup-base"
end

task :clean do
  sh "rm base/configs/ssh"
  sh "rm base/configs/ssh.pub"
end

desc "build my image"
task :build_mine do
  sh "cd mine && docker build -t adamdecaf/dev-setup ."
end

task :run_mine do
  sh "docker run -it adamdecaf/dev-setup"
end

task :default => [:build_base]
task :mine => [:build_base, :build_mine, :run_mine]
