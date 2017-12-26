#  build.js代码含义

```
'use strict'
require('./check-versions')()

process.env.NODE_ENV = 'production'

// ora是一个命令行转圈圈动画插件，好看用的
const ora = require('ora')
// rimraf插件是用来执行UNIX命令rm和-rf的用来删除文件夹和文件，清空旧的文件
const rm = require('rimraf')
// node.js路径模块
const path = require('path')
// chalk插件，用来在命令行中输入不同颜色的文字
const chalk = require('chalk')
// 引入webpack模块使用内置插件和webpack方法
const webpack = require('webpack')
// 引入config下的index.js配置文件，此配置文件我之前介绍了请自行查阅，主要配置的是一些通用的选项
const config = require('../config')
// 下面是生产模式的webpack配置文件，请看我的webpack.prod.conf解释文章
const webpackConfig = require('./webpack.prod.conf')

// 开启转圈圈动画
const spinner = ora('building for production...')
spinner.start()

// 调用rm方法，第一个参数的结果就是 dist/static，表示删除这个路径下面的所有文件
rm(path.join(config.build.assetsRoot, config.build.assetsSubDirectory), err => {
  // 如果删除的过程中出现错误，就抛出这个错误，同时程序终止
  if (err) throw err
  // 没有错误，就执行webpack编译
  webpack(webpackConfig, function (err, stats) {
    // 这个回调函数是webpack编译过程中执行
    spinner.stop()    // 停止转圈圈动画
    if (err) throw err  // 如果有错误就抛出错误

    process.stdout.write(stats.toString({
      colors: true,       // 增加控制台颜色开关
      modules: false,     // 不增加内置模块信息
      children: false,    // 不增加子级信息
      chunks: false,      // 允许较少的输出
      chunkModules: false // 不将内置模块的信息加到包信息
    }) + '\n\n')

    if (stats.hasErrors()) {
      console.log(chalk.red('  Build failed with errors.\n'))
      process.exit(1)
    }

    // 以上就是在编译过程中，持续打印消息
    // 下面是编译成功的消息
    console.log(chalk.cyan('  Build complete.\n'))
    console.log(chalk.yellow(
      '  Tip: built files are meant to be served over an HTTP server.\n' +
      '  Opening index.html over file:// won\'t work.\n'
    ))
  })
})

```