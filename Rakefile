require 'bundler/setup'

task :install => [
  :install_api,
  :install_frontend,
  :install_resolve_worker,
  :install_worker
]

task :install_api do
  sh %q{make install -C 'api-server'}
end

task :install_frontend do
  cd 'frontend' do
    sh %q{npm install}
  end
end

task :install_resolve_worker do
  sh %q{make install -C 'resolve-worker'}
end

task :install_worker do
  cd 'worker' do
    sh %q{go get github.com/mattn/gom}, noop: system('which gom')
    sh %q{gom install}
  end
end
