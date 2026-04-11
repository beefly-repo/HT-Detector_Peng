
#控制Con R G B三行的显示顺序
Order_Con_R_G_B = 'ConRGB' #'ConRGB,ConRBG,ConGRB,ConGBR,ConBRG,ConBGR' 多选一
#控制R G B行显示的颜色
color_R = (0, 0, 255) #可以更改
color_G = (0, 255, 0) #可以更改
color_B = (255, 0, 0) #可以更改
#控制No. 与cuvette之间的间距
distance_between_No_cuvette = 50 #可以更改
#控制cuvette和Con之间的间距
distance_between_cuvette_Con = 50 #可以更改
#控制Con、R、G、B之间的间距
distance_between_Con_R_G_B = 10 #可以更改

./interface.py 文件中新加了几个变量，分别是：
- Order_Con_R_G_B：控制Con R G B三行的显示顺序，可以选择 'ConRGB', 'ConRBG', 'ConGRB', 'ConGBR', 'ConBRG', 'ConBGR' 中的一个。
- color_R：控制R行显示的颜色，可以更改为其他RGB值。
- color_G：控制G行显示的颜色，可以更改为其他RGB值。
- color_B：控制B行显示的颜色，可以更改为其他RGB值。
- distance_between_No_cuvette：控制No.与cuvette之间的间距，可以更改为其他数值。
- distance_between_cuvette_Con：控制cuvette和Con之间的间距，可以更改为其他数值。
- distance_between_Con_R_G_B：控制Con、R、G、B之间的间距，可以更改为其他数值。
这些变量可以根据需要进行调整，以改变界面中各元素的显示顺序、颜色和间距。

./ultralytics/engine/results.py 文件中将导入./interface.py 文件中的新增的这些变量，他们分别是：Order_Con_R_G_B, color_R, color_G, color_B, distance_between_No_cuvette, distance_between_cuvette_Con, distance_between_Con_R_G_B。

修改./ultralytics/engine/results.py 文件中的相关代码，使其能够根据这些变量来调整识别照片中各元素的显示顺序、颜色和间距。具体来说，可以在识别图片时，根据Order_Con_R_G_B变量来确定Con R G B三行的显示顺序（'ConRGB', 'ConRBG', 'ConGRB', 'ConGBR', 'ConBRG', 'ConBGR'分别代表不同的显示顺序），并使用color_R、color_G、color_B变量来分别设置R、G、B行的颜色。同时，使用distance_between_No_cuvette、distance_between_cuvette_Con、distance_between_Con_R_G_B变量来调整No.与cuvette之间的间距、cuvette和Con之间的间距以及Con、R、G、B之间的间距。这样，界面中的元素将根据这些变量的设置进行调整，以满足用户的需求。
前提，保证不改变其他功能的前提下，进行上述修改。

#控制No Con R G B五行显示的颜色
color_No = (255, 255, 255) #可以更改
color_Con = (255, 255, 255) #可以更改
./interface.py 文件中新加了几个变量，分别是:
- color_No：控制No.行显示的颜色，可以更改为其他RGB值。
- color_Con：控制Con行显示的颜色，可以更改为其他RGB值。
在./ultralytics/engine/results.py 文件中将导入./interface.py 文件中的新增的color_No和color_Con变量，并修改相关代码，使其能够根据这些变量来调整No.行和Con行的显示颜色。具体来说，在识别图片时，使用color_No变量来设置No.行的颜色，使用color_Con变量来设置Con行的颜色。这样，界面中的No.行和Con行将根据这些变量的设置进行调整，以满足用户的需求。同时，保证不改变其他功能的前提下进行上述修改。


#显示字体大小和类型
output_font_size = 60 #可以更改
output_font = "Arial.ttf" #可以更改

在./ultralytics/engine/results.py 文件中将导入./interface.py 文件中的新增的output_font_size和output_font变量，并修改相关代码，使其能够根据这些变量来调整显示字体的大小和类型。
相关原代码中控制字体大小和类型的代码是下面这几行：
annotator = Annotator(
            deepcopy(self.orig_img if img is None else img),
            line_width,
            font_size=60,
            font="Arial.ttf",
            # pil or (pred_probs is not None and show_probs),  # Classify tasks default to pil=True
            pil=True,
            example=names,
        )


