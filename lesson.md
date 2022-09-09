<!--
 * @Author: 郑曦
 * @Date: 2022-09-09 16:04:27
 * @LastEditors: 郑曦
 * @LastEditTime: 2022-09-09 21:52:25
 * @FilePath: /rush-program/lesson.md
 * @Description: 描述
-->
1. turborepo:更快的构建monorepo的工具
2. rush本质上做大型仓库的打包工作
3. 全局安装rush npm install @microsoft/rush -g
4. 修改了rush.json或者修改了packages的内容，需要执行rush update用于更新依赖信息
5. 仓库内部的各个包之间的互相引用，需要执行命令rush add -p xx -p是安装packages的意思，测试环境需要加上--dev
6. 包的安装使用的是workspace协议，需要在rush.json内开启useWorkspace配置。
7. 给所有的子项目安装依赖，rush add -p xxx --all
8. 给单个自爆安装依赖，需要进入子项目目录下执行rush add -p xxx
9. 发包需要主动配置用户的npm token。
  9.1 执行npm whoami --registry xxx(私仓地址)，看当前账户是否正确
  9.2 查看当前登录的用户的token。cat ~/.npmrc，整行复制出authToken
  9.3 添加到.npmrc和.npmrc-public内
10. 发布命令rush publish --apply --target-branch main --publish
11. 需要将node，pnpm版本与rush.json内的配置对应上，否则可以提交成功，但是会报错。