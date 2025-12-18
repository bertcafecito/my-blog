+++
date = '{{ .Date }}'
publishDate = '{{ .Date }}'  # Post will be published on this date
draft = true
title = '{{ replace .File.ContentBaseName "-" " " | title }}'
+++
