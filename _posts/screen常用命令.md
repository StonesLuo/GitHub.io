---
layout: post
title: screen常用命令
date: 2019-07-08 15:00:11.000000000 +09:00
tags: screen, linux
---

### 1. Nnew a screen
```
screen -S sc1
```

### 2. Detach a screen
```
ctrl + a + d
```
or
```
screen -d name
```

### 3. Search the screen ids & reattach a screen
```
screen -ls
screen -r id
```

### 4. Kill a screen
```
kill -9 sc1_id
screen -wipe
```

