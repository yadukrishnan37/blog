---
title: "Building a site using Hugo Themes and deploying to GitHub Pages"
date: 2023-11-20T21:05:13+05:30

categories: []
tags: ['Discussions']
author: "Yadukrishnan P"
---

# Creating a Portfolio Using Hugo Theme as a Module

### Introduction
This article offers a simple overview of how I approached task-02: Lessgo Hugo.
The goal of the task was to create a custom portfolio using hugo sites & to deploy the same to GitHub Pages

First of all I installed hugo using **snap**:

```shell
sudo snap install hugo
```
Installing go:
```shell
sudo snap install go --classic
```
To create a new site: 
```shell
hugo new site bilberry
```
To clone the theme to the same root directory:
```shell
git clone https://github.com/Lednerb/bilberry-hugo-theme.git
```
To delete the default archetype:
```shell
rm bilberry/archetypes/default.md
```
To copy the example site content, including the config.toml file:
```shell
cp -r bilberry-hugo-theme/v4/exampleSite/* bilberry
```
Adding the theme as a hugo module:
```shell
cd bilberry
hugo mod init github.com/yadukrishnan37/bilberry
```
Installing go modules:
```shell
go mod tidy
```
To pull the theme files to add new content to the website:
```shell
hugo mod vendor
```
To run the site locally:
```shell
cd bilberry
hugo server
```

To create this article I used the following command:

```shell
hugo new article/hugobuild.md
```

Then I committed the files to a Github repo and changed the repo's build and deployment settings to GitHub actions. I then added a .yml file for deployment.
