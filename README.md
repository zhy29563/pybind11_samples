# pybind11_samples
 Learning pybind11



## 使用流程

1. 克隆或下载文件

2. 打开`vscode`安装`C/C++ Extension Pack`

3. 将`src`文件夹拖拽到`vscode`中，并在弹出的对话框中勾选选项，然后点击`是`按钮

   ![image-20210819222932576](images\image-20210819222932576.png)

4. 在`vscode`的状态栏，点击`No Kit Selected`

   ![image-20210819223533456](images\image-20210819223533456.png)

5. 在`vscode`的状态栏，点击`CMake:[Debug]:Ready`

   ![image-20210819223801131](images\image-20210819223801131.png)

6. 打开`CMakeLists.txt`文件，在第`20`行`add_library(pybind11_sample SHARED sample03.cpp)`修改`sample03.cpp`为需要进行测试的源码文件名

7. 点击`vscode`状态栏中的`Build`按钮进行生成

8. 在资源管理器中右击`SRC >> build >> Release `，并在弹出的菜单中选择`在集成终端中打开`

   ![image-20210819224308910](images\image-20210819224308910.png)

   ![image-20210819224446335](images\image-20210819224446335.png)

9. 输入`python`，然后输入`import pybind11_sample`，如果无异常，则说明生成的`pyd`库可用

   ![image-20210819224729007](images\image-20210819224729007.png)

