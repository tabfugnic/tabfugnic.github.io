namespace :new do
  desc "Create a new post"
  task :post, [:title] do |_, args|
    name = args.title.gsub(/\W/, "-").gsub(/-+/, "-").downcase
    current_time = Time.now
    formatted_time = current_time.strftime("%F")
    file_title = [formatted_time, name].join("-")
    file_path = File.join("_posts", "#{file_title}.md")
    content = <<~EOF
---
layout: post
title: #{args.title}
date: #{current_time.strftime("%FT%R")}
---
EOF
    File.open(file_path, "w") do |file|
      file.write(content)
    end
    puts "Created new post: #{file_path}"
  end
end
