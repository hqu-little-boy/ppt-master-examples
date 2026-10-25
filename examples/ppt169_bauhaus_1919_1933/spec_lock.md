<!-- ppt-master-schema: spec-lock/v1 -->
# Execution Lock

## canvas
- viewBox: 0 0 1280 720
- format: PPT 16:9

## communication
- primary_language: zh-CN
- audience: 对设计史感兴趣的大众与设计专业学生
- objective: 讲清包豪斯三阶段、预备课程与双导师制、四件代表作品及关闭后的流散，使听众能把作品与“艺术×工业”的方法联系起来并说出理念去了哪里
- core_message: 包豪斯只存在 14 年、三易其址，却把“造型教育 + 工坊生产”变成可迁移的方法，并经由流散成为现代设计的通用语法
- consumption_mode: balanced

## mode
- mode: custom
- mode_references: narrative, instructional
- mode_behavior: 叙事弧（宣言→三地十四年→方法→作品证据→1933 关闭→流散与影响），方法段按 instructional 先基础课后工坊拆解；标题写成推进的判断句，并列讲解用同构结构。

## visual_style
- visual_style: custom
- visual_style_references: editorial, photo-editorial
- visual_style_behavior: 暖白纸本底上的编辑排版：细规则线、栏线、编号 kicker、Arial Black 巨型年份锚定页面；照片做编辑式裁切——放入圆/方/三角窗口、跨越栏线或双色调满版铺底；圆、方、三角作为页面场与图片遮罩，每页至多一个主形，朱红只给一个焦点，不散布彩色几何贴纸；无阴影，层次靠规则线粗细与留白。

## colors
- background: #F2EEE5
- secondary_bg: #E4DDCF
- primary: #161616
- accent: #C23B22
- secondary_accent: #B8862B
- body_text: #1E1E1C
- secondary_text: #6B665C
- divider: #BDB5A6
- image_rendering: custom
- image_rendering_references: corporate-photo, screen-print
- image_rendering_behavior: 纪实摄影的真实材质与景深描绘无人工坊，整体压成墨黑×纸白双色调并带轻微半调网点与纸纹；安静、空旷、无文字无人物，可与历史照片同页并置。

## typography
- font_family: "Microsoft YaHei", Arial, sans-serif
- title_family: "Microsoft YaHei", Arial, sans-serif
- body_family: "Microsoft YaHei", Arial, sans-serif
- display_family: "Arial Black", "Microsoft YaHei", sans-serif
- quote_family: SimSun, Cambria, serif
- body: 22
- title: 40
- subtitle: 28
- lead: 26
- annotation: 16
- footnote: 13
- cover_title: 72
- display: 120
- quote: 34
- kicker: 15

## icons
- library: none
- inventory: none

## images
- dessau_duotone: images/dessau_duotone.jpg | source=web | crop=adaptive
- dessau_building: images/dessau_building.jpg | source=web | crop=adaptive
- feininger_cathedral: images/feininger_cathedral.jpg | source=web | crop=no-crop
- workshop_scene: images/workshop_scene.jpg | source=ai | crop=adaptive
- mt8_lamp: images/mt8_lamp.jpg | source=web | crop=adaptive
- wassily_chair: images/wassily_chair.jpg | source=web | crop=adaptive
- tel_aviv_white_city: images/tel_aviv_white_city.jpg | source=web | crop=adaptive

## page_rhythm
- P01: anchor
- P02: breathing
- P03: dense
- P04: dense
- P05: dense
- P06: dense
- P07: anchor
- P08: dense
- P09: dense
- P10: dense
- P11: breathing
- P12: dense
- P13: anchor

## page_visualizations
- P03: chart/gantt_chart

## pptx_structure
- mode: flat

## forbidden
- `mask`, `<style>`, `class`, external CSS, `<foreignObject>`, `textPath`, `@font-face`, `<animate*>`, `<set>`, `<script>` / event attributes, `<iframe>`
- HTML named entities in text; write typography as raw Unicode and escape XML reserved characters
