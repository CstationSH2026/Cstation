# 洗浴预约应用集成指南

如果您已经有一个现有的网站，并且不想覆盖现有的 `index.html` 文件，本指南将帮助您将洗浴预约应用集成到您的网站中。

## 方法一：创建独立的预约页面

这种方法最简单，不需要修改您现有的 `index.html` 文件。

1. **上传文件**：
   - 将 `shower_booking_app_v2.zip` 文件解压
   - 将解压后的所有文件上传到您的网站根目录

2. **重命名主文件**：
   - 将 `index.html` 重命名为 `booking.html`（或任何您喜欢的名称）
   - 保持其他文件的名称不变

3. **创建链接**：
   - 在您现有的 `index.html` 文件中添加一个链接，指向预约页面：
   ```html
   <a href="booking.html" class="btn">洗浴预约</a>
   ```

4. **完成**：
   - 现在，访问者可以通过点击链接进入预约页面

## 方法二：使用iframe嵌入

如果您希望在现有页面中直接显示预约功能，可以使用iframe。

1. **上传文件**：
   - 将 `shower_booking_app_v2.zip` 文件解压
   - 将解压后的所有文件上传到您的网站根目录

2. **重命名主文件**：
   - 将 `index.html` 重命名为 `booking.html`

3. **嵌入iframe**：
   - 在您现有的 `index.html` 文件中添加以下代码：
   ```html
   <div class="booking-container" style="width: 100%; max-width: 480px; margin: 0 auto;">
     <iframe src="booking.html" width="100%" height="800px" frameborder="0" style="border: none;"></iframe>
   </div>
   ```

4. **调整样式**：
   - 根据需要调整容器的宽度、高度和其他样式

## 方法三：使用弹出窗口

如果您希望通过点击按钮打开预约功能，可以使用弹出窗口。

1. **上传文件**：
   - 将 `shower_booking_app_v2.zip` 文件解压
   - 将解压后的所有文件上传到您的网站根目录

2. **重命名主文件**：
   - 将 `index.html` 重命名为 `booking.html`

3. **添加按钮和脚本**：
   - 在您现有的 `index.html` 文件中添加以下代码：
   ```html
   <button id="bookingBtn" class="btn">打开洗浴预约</button>

   <script>
   document.getElementById('bookingBtn').addEventListener('click', function() {
     window.open('booking.html', '_blank', 'width=500,height=850,top=100,left=100');
   });
   </script>
   ```

## 方法四：使用JavaScript动态加载

这种方法比较复杂，但可以提供更好的用户体验。

1. **上传文件**：
   - 将 `shower_booking_app_v2.zip` 文件解压
   - 将解压后的所有文件上传到您的网站根目录

2. **重命名主文件**：
   - 将 `index.html` 重命名为 `booking.html`

3. **添加模态框和脚本**：
   - 在您现有的 `index.html` 文件中添加以下代码：
   ```html
   <!-- 模态框容器 -->
   <div id="bookingModal" class="modal" style="display: none; position: fixed; z-index: 9999; left: 0; top: 0; width: 100%; height: 100%; overflow: auto; background-color: rgba(0,0,0,0.5);">
     <div class="modal-content" style="background-color: #fefefe; margin: 5% auto; padding: 0; border: 1px solid #888; width: 90%; max-width: 480px; border-radius: 10px; overflow: hidden;">
       <div class="modal-header" style="padding: 10px 15px; background-color: #1A3C34; color: white; display: flex; justify-content: space-between; align-items: center;">
         <h3 style="margin: 0;">洗浴预约</h3>
         <span class="close" style="color: white; font-size: 28px; font-weight: bold; cursor: pointer;">&times;</span>
       </div>
       <div class="modal-body" style="padding: 0;">
         <iframe id="bookingFrame" src="booking.html" width="100%" height="700px" frameborder="0" style="border: none;"></iframe>
       </div>
     </div>
   </div>

   <!-- 打开按钮 -->
   <button id="openBookingBtn" class="btn">打开洗浴预约</button>

   <script>
   // 获取模态框
   var modal = document.getElementById("bookingModal");
   
   // 获取打开按钮
   var btn = document.getElementById("openBookingBtn");
   
   // 获取关闭按钮
   var span = document.getElementsByClassName("close")[0];
   
   // 点击按钮打开模态框
   btn.onclick = function() {
     modal.style.display = "block";
   }
   
   // 点击关闭按钮关闭模态框
   span.onclick = function() {
     modal.style.display = "none";
   }
   
   // 点击模态框外部关闭模态框
   window.onclick = function(event) {
     if (event.target == modal) {
       modal.style.display = "none";
     }
   }
   </script>
   ```

## 注意事项

1. **文件路径**：
   - 确保所有文件的路径正确，特别是CSS、JavaScript和图片文件

2. **响应式设计**：
   - 预约应用已经是响应式设计，可以适应不同屏幕大小
   - 如果使用iframe或模态框，请确保容器也具有响应式特性

3. **Firebase配置**：
   - 如果您使用的是多用户版本，请确保正确配置了Firebase

4. **测试**：
   - 在不同设备和浏览器上测试集成效果
   - 确保所有功能正常工作，包括表单提交和数据导出

如果您在集成过程中遇到任何问题，请参考项目中的其他文档或联系技术支持。