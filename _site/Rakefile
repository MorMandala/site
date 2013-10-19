desc "Publish site to gh-pages"
task :publish do
    sha = `git log`.match(/[a-z0-9]{40}/)[0]
    sh "jekyll build"
    sh "git checkout gh-pages"
    sh "git checkout master -- _site/"
    sh "cp -r _site/* ."
    sh "git add ."
    sh "git commit -m 'Updating content from #{sha} on master.'"
    sh "git push origin gh-pages"
    sh "git checkout master"
end
