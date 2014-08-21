Capistrano Awesome
==================

## Tasks

If your version is greater than or equal to 3.2.1, use `.rake` as an extension of the task, if less use `.cap`, for more details [see here](https://github.com/capistrano/capistrano/commit/7e41233d76fec0aca6877b62b876b7e2c9b85ec0).

    $ cap -V
    Capistrano Version: 3.2.1
    
    $ ls -d $PWD/*
    /home/joridos/Documents/bitbucket/project/lib/capistrano/tasks/db_backup.rake
    /home/joridos/Documents/bitbucket/project/lib/capistrano/tasks/other_task.rake


    $ cap -V
    Capistrano Version: 3.2.0
    
    $ ls -d $PWD/*
    /home/joridos/Documents/bitbucket/project/lib/capistrano/tasks/db_backup.cap
    /home/joridos/Documents/bitbucket/project/lib/capistrano/tasks/other_task.cap

Passing parameter to task on the command line.

    namespace :project do
      desc 'Print a word'
      task :print do
        on roles(:all), in: :parallel do
          execute :echo, "the word is: #{ENV['word']}"
        end
      end
    end
``` shell    
$cap stage project:print word=foo
```
