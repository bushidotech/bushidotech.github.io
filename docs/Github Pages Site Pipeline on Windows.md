
## Prerequisites
* obsidian install
* Obsidian settings - relative referencing to links, github flavored markdown, local assets folder
* basic markdown knowledge
* git install
* gitbash install
* Basic git knowledge
* Github account
* Github Pages repo
* SSH key generated and loaded to github account


## 1. Write Markdown posts in Obsidian
* Create a new folder in obsidian for posts that you wish to copy into your local repo
* copy the path to the folder for later
```
~/Documents/Obsidian Vault/Posts to copy
```
* In VSCode, right click the workspace on the left and click 'add folder to workspcace'
* navigate to the obsidian Vault and chosen posts folder
![](assets/open_directory_vscode.png)
* Now every obsidian post within that directory will automatically show up in your VSCode editor
## 2. Sync posts with my local site repo
* For simplicity, I decided to open the obsidian vault directly in VScode. This allows me to use simple bash commands to copy posts from the obsidian vault directory to my local site repo

## 3. Ensure all links to posts and images work Interchangeably

* When a page is posted to Github, normal Github Flavored Markdown links will work within the github repo.
* However, for the github pages pipeline, this will not work. This is because in the background, Github is using Jekyll to convert all your .md files to html so a reference to a local .md wont work. 
* The jekyl relative links plugin will fix this

#### 1. Enable Jekyll Relative Links Plugin in _congif.yml

```_config.yml
plugins:
  - jekyll-relative-links

relative_links:
  enabled: true
  collections: true
```
* just add this anywhere in the .yml file
#### 2. Format relative links for the plugin
```
[linktest](subfolder/page.md)
```
* Now pages will render proper relative links to your github repo


## 4. Organize the Repo Structure
