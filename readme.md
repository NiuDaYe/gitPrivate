项目开发流程

一、私仓搭建
1: 全局安装 npm install -g verdaccio
2: 启动verdaccio:  pm2 start verdaccio
3: 访问 http://localhost:4873

二、设置登录账号
pnpm set registry http://localhost:4873/
pnpm adduser --registry http://localhost:4873/
设置用户名密码 然后登录。

三、创建包并发布包到私仓
1: 初始化项目 pnpm init
2: 新建 pnpm-workspace.yaml文件
3: lerna init --independent
4: 在component下执行  lerna add @niu/hooks
  4-1: 然后在component/index.js引入 import hook from "@niu/hooks";
  4-2: 然后在component下执行node index.js打印
5: lerna publish from-package
6: 再访问 http://localhost:4873

四、移除包
pnpm unpublish @niu/hooks

五、完善项目
  注：pnpm add typescript -r/-w 为每个项目/为全局添加依赖

pnpm add typescript -D -w

六、提交代码到Git

七、lerna publish 到私仓

   查看: http://localhost:4873



pnpm remove @niu/hooks --filter @niu/components