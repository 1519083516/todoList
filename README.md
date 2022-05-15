# todoList
用vue实现todoList功能

## 组件（App管理）
* MyHeader-输入框
* MyList-内容区
  * MyItem-todo项，包含复选框，标签和删除按钮
* MyFooter-底部，包含全部todo，及已完成todo数据统计，复选框和删除已完成任务按钮

## 功能实现
* 输入框中输入内容按下Enter后添加todo项，若内容为空则弹出提醒：输入内容不可为空；且输入内容情况。
* 选中todo项复选框时，发生数据响应，悬停在todo项右侧时删除按钮出现，点击则弹出确认弹框，按下删除该todo项。
* 当todo项为0时，MyList类名从todo-main改为todo-empty，MyFooter隐藏。
* 在底部统计todo全部数量和已完成数量，点击复选框，实现todo项全选or全不选中，点击右侧删除已完成任务按钮，删除已完成todo。
