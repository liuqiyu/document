# 一些需要注意的小技巧


1. 避免git多人开发存在冲突，在`.gitignore`文件中添加以下代码
```
// # Editor directories and files
// .idea
// .vscode
// *.suo
// *.ntvs*
// *.njsproj
// *.sln

// 若添加后还存在.workspace.xml冲突问题，

git  rm -r --cached .idea    
```
