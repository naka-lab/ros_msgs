# ros_msgs
研究室で使用する独自定義のメッセージ・サービスを共有するためのリポジトリ

## 使い方
1. リポジトリのclone 
    ```
    cd ~/catkin_ws/src
    git clone https://github.com/naka-lab/ros_msgs.git
    ```

2. catkin_make
    ```
    cd ~/catkin_ws
    catkin_make -DCATKIN_WHITELIST_PACKAGES="ros_msgs"
    ```

## 新たなメッセージ・サービスの追加
1. srvまたはmsgフォルダに定義ファイル（*.srv, *.msg）を追加

2. CMakeLists.txtに`add_message_files`または`add_service_files`定義ファイルの名前を追加
    ```
    add_message_files(
      FILES
      Message1.msg
      Message2.msg
    )
    ```
    ```
    add_service_files(
       FILES
       StringTrigger.srv
       Service1.srv
    )
    ```

3. catkin_make
    ```
    cd ~/catkin_ws
    catkin_make -DCATKIN_WHITELIST_PACKAGES="ros_msgs"
    ```

4. 他の人と共有する場合はgithubへpushする
    ```
    ~/catkin_ws/src/ros_msgs
    git add .
    git commit -m "add files"
    git push
    ```
