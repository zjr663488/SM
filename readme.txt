给定的程序(IoU_calculator.exe)是一个简单的 IoU（Intersection over Union）计算器，用于计算两个边界框之间的 IoU 值。用户可以通过选择一个txt文件，输入包含边界框的信息，并计算它们与预定义的 ground truth 边界框之间的 IoU 匹配情况。

使用说明
程序会弹出一个窗口，窗口标题为 "IoU Calculator"。
点击 "Open File" 按钮，选择包含边界框信息的文本文件。
文本文件格式为每行一个边界框信息，包括 图片ID、左上角和右下角坐标。
程序会读取文本文件中的边界框信息，并计算它们与对应的 ground truth 边界框之间的 IoU 值。
结果会显示在窗口中，包括输入的总 ID 数、有效的 ID 数、有效 ID 的平均 IoU、output.txt的路径。

输入：
使用txt文档作为输入，其中格式如下：
ID x1 y1 x2 y2

例：
0_11_11650 20 10 299 194
0_23_23748 50 60 189 236
1_25_25257 80 50 118 276

输出:
Total ID count:  (输入的所有图片ID个数）
Valid ID count: (输入的ID格式正确的id个数）/1000 (1000张图片)
Average IoU for valid IDs: (有效 ID 的平均 IoU)
output.txt Path: (显示output.txt路径，在当前可执行文件文件夹下)

output.txt 输出每个图片的id和iou，格式如下：
ID：___ IoU：___

Total ID count:  ___
Valid ID count:  ___ /1000 
Average IoU for valid IDs: ___

注意事项
1. 程序处理文本文件中的边界框信息时，会检查 ID 是否已经存在，以及计算每个边界框与 ground truth 边界框的 IoU 值。
2. 如果输入的ID重复，程序只识别第一次识别到的ID及其对应的坐标，跳过再次识别到的ID。
3. 如果输入的ID错误，程序会跳过当前错误ID，继续读入下一行信息。
4. 如果输入的坐标信息少于或多于四个，程序会显示出现错误的ID，并跳过该行。
5. 错误信息会在 GUI 界面中以红色显示。
6. 程序会根据文本文件中的边界框信息计算各种统计数据，并在 GUI 界面中显示。


