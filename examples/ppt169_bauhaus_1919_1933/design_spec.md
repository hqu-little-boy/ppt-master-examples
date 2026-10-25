<!-- ppt-master-schema: design-spec/v1 -->
# 包豪斯 1919–1933 - Design Spec

## I. Project Information

| Item | Value |
| --- | --- |
| Project Name | bauhaus_1919_1933_ppt169 |
| Canvas Format | ppt169 (1280×720) |
| Page Count | 13 |
| Primary Language | zh-CN |
| Target Audience | 对设计史感兴趣的大众与设计专业学生：听过“包豪斯”这个词，熟悉现代家具与无衬线字体的样子，但不清楚学校本身的时间线、制度与人物 |
| Communication Intent | 先讲清一所学校的来龙去脉（三地、三任校长、关闭），再解释它真正的发明——预备课程与工坊双导师制，用四件代表作品让方法可见，最后说明流散如何把方法带到世界 |
| Desired Audience Outcome | 听众能说出魏玛→德绍→柏林三阶段与年份，说出预备课程与双导师制如何运作，能把台灯、钢管椅、通用字体、德绍校舍与“艺术×工业”的方法联系起来，并知道关闭后理念经由谁、去了哪里 |
| Core Message / Ask / Action | 包豪斯只存在了 14 年、三易其址，但它把“造型教育 + 工坊生产”变成了一套可迁移的方法；1933 年的关闭反而让这套方法随师生流散，成为现代设计的通用语法 |
| Delivery Context | 主要为讲者主导的 25 分钟设计史讲座/课堂；次要为会后独立翻阅的专题讲义 |
| Artifact Afterlife | 作为设计史课程讲义与 ppt-master 示例 deck 留存，出处需可追溯 |
| Reading Mode | balanced |
| Content Strategy | balanced（未填 content_divergence）：以叙事弧重组研究材料，保留全部事实与出处，不引入研究外数字 |
| Design Style | 设计史档案册（custom）：纸本编辑排版 + 编辑式摄影裁切，包豪斯基本形作为页面场与图片窗口 |
| AI Image Acquisition Path | auto |
| Generation Mode | continuous |
| Spec Refinement | disabled |
| Speaker Notes | enabled — explicit user instruction（任务书：Speaker Notes=true） |
| Custom Animations | enabled — explicit user instruction（任务书：Custom Animations=true，相邻页 Morph ≥2 处） |
| Narration Audio | disabled — explicit user instruction（任务书：Narration Audio=false） |
| Created Date | 2026-10-24 |

- **Confirmation provenance**: 用户把确认门明确委派给执行代理；Stage 1 选 `free_design`（无模板意图、无 workspace root），不启动 Confirm UI，无 UI 回执。Stage 2 三个方向：① 设计史档案册（选中）；② 构成主义暗场——墨黑底、海报式巨型年份与粗规则线、vintage-poster 渲染，放弃：暗场压低照片与纸本质感，且易滑向“海报贴纸”；③ 工坊纸样——纸雕层叠与柔和投影、paper-cut 渲染，放弃：亲和但与包豪斯机械精确的气质相悖。选①理由：受众是读者+听众双重身份，纸本编辑排版最接近“设计史专题”，基本形承担图片窗口与页面场，而不是装饰贴纸。

## II. Canvas Specification

| Property | Value |
| --- | --- |
| Format | PPT 16:9 |
| Dimensions | 1280 × 720 |
| viewBox | `0 0 1280 720` |
| Margins | 64 px left/right, 56 px top, 48 px bottom |
| Content Area | x 64–1216, y 56–672 |

## III. Visual Theme

### Theme Style

- **Mode**: custom
- **Mode References**: narrative, instructional
- **Mode Behavior**: 整体走叙事弧——1919 年的宣言（起）→ 三地十四年（展开）→ 方法：预备课程与双导师制（核心讲解，按 instructional 拆解顺序：先基础课再工坊）→ 四件作品作为方法的证据 → 1933 年关闭（转折）→ 流散与影响（解决）；标题写成推进的判断句，讲解页用并列结构便于比较。
- **Visual style**: custom
- **Visual Style References**: editorial, photo-editorial
- **Visual Style Behavior**: 暖白纸本底色上的编辑排版：细规则线、栏线、小号编号 kicker、大号年份数字（Arial Black）锚定页面；照片做编辑式裁切——放进圆/方/三角窗口、跨越栏线、或以双色调（墨黑×纸白）满版铺底；圆、方、三角作为页面场与图片遮罩出现，每页至多一个主形，红色只用于一个焦点，绝不散布成彩色几何贴纸；无阴影，层次靠规则线粗细与留白。
- **Theme**: 设计史专题刊物——像一本印刷精良的包豪斯展览图录
- **Tone**: 冷静、精确、带一点印刷品的温度

### Color Scheme

| Role | HEX | Purpose |
| --- | --- | --- |
| Background | #F2EEE5 | 暖白纸本主底 |
| Secondary background | #E4DDCF | 次级纸面、图注底、分区色块 |
| Primary | #161616 | 墨黑：标题、粗规则线、暗场页底、双色调暗部 |
| Accent | #C23B22 | 朱红：每页唯一焦点（一个圆、一条线、一个年份） |
| Secondary accent | #B8862B | 赭黄：次级标记（阶段标签、时间刻度），用量少于朱红 |
| Body text | #1E1E1C | 正文 |
| Secondary text | #6B665C | 图注、出处、注释 |
| Divider | #BDB5A6 | 细规则线、栏线 |

### AI Image Strategy

- **Image Rendering**: custom
- **Image Rendering References**: corporate-photo, screen-print
- **Image Rendering Behavior**: 以纪实摄影的真实材质与景深描绘无人的工坊场景（corporate-photo 负责光线、景深与材质真实感），再整体压成墨黑×纸白的双色调并带轻微半调网点与纸纹（screen-print 负责有限色与印刷质感）；画面安静、空旷、无文字无人物，可与 Commons 的历史照片同页并置而不突兀。
- **Visual**: 晨光中的空旷工坊——织机、金属车床、木工台，双色调印刷质感
- **Mood**: 像展览图录里一张翻拍的旧照片：安静、克制、有温度

## IV. Typography System

### Font Plan

| Role | Character (Reference) | Primary | English if non-English | Fallback tail |
| --- | --- | --- | --- | --- |
| Title | 几何无衬线粗体，呼应拜耳的无衬线主张 | Microsoft YaHei | Arial | sans-serif |
| Body | 中性无衬线 | Microsoft YaHei | Arial | sans-serif |
| Display | 海报黑体，用于巨型年份与编号 | Microsoft YaHei | Arial Black | sans-serif |
| Quote | 衬线引文，宣言与名句 | SimSun | Cambria | serif |

- **Title stack**: "Microsoft YaHei", Arial, sans-serif
- **Body stack**: "Microsoft YaHei", Arial, sans-serif
- **Display stack**: "Arial Black", "Microsoft YaHei", sans-serif
- **Quote stack**: SimSun, Cambria, serif
- **Role rationale**: Display 让 1919/1925/1933 等年份成为页面锚点；Quote 用衬线与无衬线形成编辑式对照，只用于宣言与引语。

### Font Size Hierarchy

| Purpose | Anchor Size (px) |
| --- | ---: |
| Body | 22 |
| Title | 40 |
| Subtitle | 28 |
| Lead | 26 |
| Annotation | 16 |
| Footnote | 13 |
| Cover title | 72 |
| Display | 120 |
| Quote | 34 |
| Kicker | 15 |

## V. Layout Principles

### Deck-wide Direction

- **Hierarchy direction**: kicker（编号+章节）→ 判断句标题 → 一个焦点（年份/图片/基本形）→ 正文与图注
- **Composition tendency**: 不对称编辑栏；照片跨栏或嵌入基本形窗口；暗场页（P11）与满版照片页（P07）打断纸本节奏
- **Cross-page continuity**: 朱红圆作为贯穿母题——封面的大红圆在 P02 缩为宣言页的印章；作品三页（P08–P10）共用同一“展台”结构：左侧对象窗口的基本形依次由圆→方→三角变化；页眉统一一条细规则线 + 页码 + “BAUHAUS 1919–1933”
- **Spacing posture**: 按节奏变化——dense 页紧凑，anchor/breathing 页大留白
- **Spacing anchors**: page margin 64 px · block gap 32 px · column gutter 40 px · corner radius 0 px · body leading 1.5

## VI. Icon Usage Specification

- **Primary bundled library**: none

| Icon Path | Suitable Scenarios |
| --- | --- |

## VII. Visualization Reference List

| Page | Family | Template | Usage |
| --- | --- | --- | --- |
| P03 | chart | gantt_chart | 把魏玛、德绍、柏林三阶段与三任校长任期按真实年份长度排在同一时间轴上 |

## VIII. Image Resource List

| Filename | Dimensions | Ratio | Purpose | Type | Image pattern | Crop Policy | Acquire Via | Status | Reference | text_policy | page_role |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| dessau_building.jpg | 3827×2983 | 1.28 | 德绍校舍原图（衍生母本，P07 原色使用） | Photo | 满版铺底，工坊翼玻璃幕墙占画面右侧，标题落在左侧天空/暗区 | adaptive | web | Sourced | Bauhaus Dessau building by Walter Gropius, exterior, workshop wing glass curtain wall and bridge visible, daylight, Wikimedia Commons CC/PD | none | local |
| dessau_duotone.jpg | 1800×1403 | 1.28 | 封面主视觉：校舍双色调 | Photo | 放进巨型方形窗口，朱红圆压住一角形成封面钩子 | adaptive | web | Sourced | Derived from dessau_building.jpg; treatment=duotone; 墨黑 #161616 × 纸白 #F2EEE5 | none | local |
| feininger_cathedral.jpg | 3272×4912 | 0.67 | P02 宣言封面木刻《大教堂》 | Artwork | 完整展示作品（不裁），旁边是衬线宣言引文 | no-crop | web | Sourced | Lyonel Feininger, Cathedral (Kathedrale), woodcut, title page of the Bauhaus Manifesto 1919, Wikimedia Commons public domain scan | none | local |
| workshop_scene.jpg | 2752×1536 | 1.79 | P05 工坊场景氛围图 | Scene | 放进右侧大矩形窗口并被一条栏线切开，左侧为工坊双导师结构 | adaptive | ai | Generated | 空旷的魏玛时代工坊：前景木质织机与纱线，中景金属工坊的车床与铜器，晨光从高窗斜射；无人物、无文字、无标识；四周留出安静暗部便于裁切 | none | local |
| mt8_lamp.jpg | 2152×1908 | 1.13 | P08 瓦根菲尔德台灯 | Product | 放进圆形窗口，灯罩球体与圆形窗口同心 | adaptive | web | Sourced | Wagenfeld table lamp MT8 / WG24, glass base, opal glass dome, chrome shaft, isolated or museum shot, Wikimedia Commons CC | none | local |
| wassily_chair.jpg | 2500×1953 | 1.28 | P09 布劳耶 B3 钢管椅 | Product | 放进方形窗口，椅子钢管与方框对齐 | adaptive | web | Sourced | Marcel Breuer Wassily chair B3, chrome tubular steel and black leather, three-quarter view, plain background, Wikimedia Commons CC | none | local |
| tel_aviv_white_city.jpg | 3264×2448 | 1.33 | P12 特拉维夫白城建筑（流散的落点之一） | Photo | 嵌入三角/梯形窗口，成为路线图的一个落点 | adaptive | web | Sourced | White City Tel Aviv Bauhaus International Style building, curved balconies, white facade, Wikimedia Commons CC | none | local |

- **Plan repair (2026-10-24, Step 5)**: bauhaus_masters_1926.jpg 在 Wikimedia/Openverse 多组变体与翻页后无合格候选；bayer_universal.png 原稿受版权保护（拜耳 1985 年去世），开放许可库中无此图。两行移出计划：P06 改为纯排版人物索引，P10 改用原生字母样张示意。

## IX. Content Outline

### Part 1: 起点

#### Slide 01 - 封面

- **Audience move**: 只知道“包豪斯是一种风格” → 意识到它是一所只存在 14 年的学校
- **Relationships**: 标题、年份区间与“14 年”钩子并列；校舍图是学校身份的证据
- **Composition**: 大方形窗口装入双色调德绍校舍，一枚朱红大圆压住窗口一角；巨型年份“1919–1933”与标题落在纸本留白中
- **Title**: 包豪斯 1919–1933
- **Core message**: 一所只存在 14 年的学校，改变了一个世纪的设计
- **Content**: 主标题“包豪斯 1919–1933” · 副标题“一所学校如何成为现代设计的通用语法” · 钩子“14 年 · 3 座城市 · 3 任校长”
- **Cover impact**: 钩子 =“14 年”与德绍校舍；构图为 Reference
- **Images**: dessau_duotone.jpg
- **Motion suggestion**: 朱红大圆在 P02 缩小为宣言页的印章（Morph 候选）
- **Fact IDs**: F004, F005

#### Slide 02 - 1919 宣言

- **Audience move**: 不知道学校为何创办 → 明白它从一份“回到工坊”的宣言开始
- **Relationships**: 宣言引文 ← 封面木刻（link）；两所学校合并 → 包豪斯（order）
- **Composition**: 左侧完整展示费宁格木刻，右侧衬线大引文，朱红小圆作印章
- **Title**: 一切从一句话开始
- **Core message**: 1919 年 4 月 1 日，格罗皮乌斯合并两所学校，宣言号召艺术家回到工坊
- **Content**: 引文“一切造型活动的最终目标是建筑！”（德文原句小字） · 1919.4.1 魏玛：美术学院 + 工艺美术学校 → 国立包豪斯 · 封面：费宁格木刻《大教堂》，原题《社会主义大教堂》
- **Images**: feininger_cathedral.jpg
- **Motion suggestion**: 承接 P01 的朱红圆（Morph 端点）
- **Fact IDs**: F001, F002, F003

#### Slide 03 - 三地十四年

- **Audience move**: 把包豪斯当成一个静止的风格 → 看到它在三座城市、三任校长之间不断迁移
- **Relationships**: 魏玛 → 德绍 → 柏林（order）；三任校长任期与三阶段重叠但边界不同（overlap）；迁校原因（link）
- **Composition**: 一条按真实年份比例的时间轴，三段阶段条在上，三任校长任期条在下，每段配圆/方/三角作为阶段记号
- **Title**: 三座城市，十四年
- **Core message**: 学校每一次搬迁都伴随着政治压力，校长的更替与城市的更替并不同步
- **Content**: 魏玛 1919–1925 · 德绍 1925–1932 · 柏林 1932–1933 / 格罗皮乌斯 1919–1928 · 迈耶 1928–1930 · 密斯 1930–1933 / 注：1930 年迈耶被市长解聘；1932 年纳粹党接管安哈尔特州后德绍关闭
- **Visualization**: phases-timeline：阶段与校长任期两行甘特式时间轴（1919–1933 刻度）
- **Native-ready**: phases-timeline=no
- **Motion suggestion**: 阶段条按时间顺序展开，校长任期随后出现
- **Fact IDs**: F004, F005, F016, F017, F030

### Part 2: 方法

#### Slide 04 - 预备课程

- **Audience move**: 以为包豪斯直接教“设计” → 理解所有人先过一道共同的基础课
- **Relationships**: 预备课程是进入工坊的前提（order）；伊顿 → 莫霍利-纳吉 + 阿尔伯斯（order，主持者更替）；课程核心指向“建筑”（parent）
- **Composition**: 同心环结构：外环预备课程，中环材料/形式/色彩研究与工坊，圆心“建筑”；右侧窄栏记录主持者更替
- **Title**: 先上同一门基础课
- **Core message**: 学生必须先通过预备课程，才有资格选择工坊；这门课的主持者从伊顿换成了莫霍利-纳吉和阿尔伯斯
- **Content**: 规则：通过预备课程 → 选择工坊进入主课程 · 伊顿（1919–1923）：自然与材料研究、色彩与形式理论、古代大师作品分析、写生 · 1923 年后：莫霍利-纳吉重写课程，与阿尔伯斯共同主持 · 宣言的终点：建筑
- **Motion suggestion**: 由外环向圆心依次显现，讲解学习顺序
- **Fact IDs**: F007, F008, F002

#### Slide 05 - 工坊与双导师

- **Audience move**: 不清楚“工坊”如何教学 → 理解形式导师与工艺导师共同带一个工坊
- **Relationships**: 每个工坊 = 形式导师 + 工艺导师（membership）；例：玻璃画工坊 克利 / 阿尔伯斯；织造工坊 施特尔策尔成为首位女性导师（contrast：从学生到导师）
- **Composition**: 左侧双栏结构图（形式导师 | 工艺导师 → 工坊 → 产品），右侧大窗口放工坊场景图
- **Title**: 一个工坊，两位导师
- **Core message**: 艺术家负责形式，工匠负责工艺——双导师制把艺术与生产绑在同一张工作台上
- **Content**: 形式导师：艺术家（如克利）· 工艺导师：工匠（如 1923 年起的阿尔伯斯）· 例：玻璃画工坊 · 施特尔策尔：1919 年入学，1927 年成为织造工坊青年导师，首位获“导师”头衔的女性 · 1923 年展览（含号角屋）是州政府继续资助的条件
- **Images**: workshop_scene.jpg
- **Fact IDs**: F009, F028, F010

#### Slide 06 - 人物

- **Audience move**: 只认识一两个名字 → 能把关键人物与他们在学校里的角色对上号
- **Relationships**: 校长（格罗皮乌斯、迈耶、密斯）与教师（伊顿、克利、康定斯基、莫霍利-纳吉、阿尔伯斯、施特尔策尔）两组（membership）；加入年份顺序（order）
- **Composition**: 纯排版人物索引：两组（校长 / 教师）按加入年份排在一条年份标尺上，每人一个基本形标记与一句角色说明；无照片
- **Title**: 谁在这里教书
- **Core message**: 包豪斯把当时最激进的画家请进了工坊
- **Content**: 校长：格罗皮乌斯 1919–1928 · 迈耶 1928–1930 · 密斯 1930–1933 / 教师：伊顿 1919 预备课程 · 克利 1920 · 康定斯基 1922 · 莫霍利-纳吉 1923 重写预备课程 · 阿尔伯斯 1920 入学，1923 起执教 · 施特尔策尔 1927 织造导师
- **Fact IDs**: F005, F006, F007, F008, F022, F028

### Part 3: 作品

#### Slide 07 - 德绍校舍

- **Audience move**: 把校舍当作一张常见照片 → 读懂它本身就是学校的宣言
- **Relationships**: 工坊翼、桥楼、普雷勒楼三部分（membership）；动工 → 封顶 → 落成（order）
- **Composition**: 满版校舍照片，左侧暗区放标题与三个日期，小号图注标出三部分
- **Title**: 校舍本身就是宣言
- **Core message**: 1926 年落成的德绍校舍把玻璃、钢与功能分区变成了可以走进去的教材
- **Content**: 1925.9 动工 · 1926.3.21 封顶 · 1926.12.4 落成 / 工坊翼：贯通三层的玻璃幕墙 · 普雷勒楼：五层，28 间师生工作室 · 桥楼：行政与格罗皮乌斯的建筑事务所 · 1996 年列入世界遗产
- **Images**: dessau_building.jpg
- **Fact IDs**: F011, F012, F027

#### Slide 08 - MT8 台灯

- **Audience move**: 把台灯当成普通灯具 → 看出它是圆、柱、球的组合，也是工业化的第一次碰壁
- **Relationships**: 圆形底座 · 圆柱灯杆 · 球形灯罩（membership）；理想（工业产品）与现实（手工组装）的对照（contrast）
- **Composition**: 作品展台结构：左侧圆形窗口装台灯，右侧作品卡片（年份、设计者、材料、故事）
- **Title**: 一盏灯里的圆、柱、球
- **Core message**: 1924 年的 MT8 台灯以纯几何形构成，却因仍靠手工组装而推销失败
- **Content**: 瓦根菲尔德 + 尤克尔 · 魏玛金属工坊 · 1924 年春首批 · 金属底座与玻璃底座两版 · 初期推销失败：零件仍靠手工组装
- **Images**: mt8_lamp.jpg
- **Motion suggestion**: 作品展台结构延续到 P09，圆形窗口变为方形窗口（Morph 候选）
- **Fact IDs**: F013

#### Slide 09 - B3 钢管椅

- **Audience move**: 只把它当作经典家具 → 知道它来自一辆自行车带来的材料灵感
- **Relationships**: 自行车车架 → 钢管家具（link）；P08 展台结构延续（order）
- **Composition**: 同一展台结构，窗口变为方形装钢管椅；一条细线把“自行车”与“椅子”连起来
- **Title**: 从自行车到椅子
- **Core message**: 布劳耶在德绍家具工坊把自行车的钢管车架变成了座椅结构
- **Content**: 布劳耶 · 德绍家具工坊负责人 · 1925–1926 · B3（后称瓦西里椅）· 灵感：1925 年买的第一辆自行车 · 早期版本由 Thonet 生产
- **Images**: wassily_chair.jpg
- **Motion suggestion**: 承接 P08 展台（Morph 端点），并在 P10 窗口变为三角
- **Fact IDs**: F014

#### Slide 10 - 通用字体

- **Audience move**: 以为字体只是风格 → 理解拜耳想用“去掉大写”来简化书写
- **Relationships**: 取消大写 → 书写更高效（link）；设计稿与从未铸字的对照（contrast）
- **Composition**: 同一展台结构，三角窗口内放原生超大小写字母样张（以几何无衬线示意，不冒充拜耳原稿）；右侧作品卡片
- **Title**: 只用小写字母
- **Core message**: 1925 年起，拜耳设计的“通用字体”取消大写，主张更高效的书写，却始终停留在纸上
- **Content**: 拜耳 · 1925 年起 · 几何无衬线 · 取消大写字母 · 只存在于设计稿，从未铸字 · 1928 年离开包豪斯
- **Motion suggestion**: 承接 P09 展台（Morph 端点）
- **Fact IDs**: F015

### Part 4: 关闭与流散

#### Slide 11 - 关闭

- **Audience move**: 以为学校自然结束 → 知道它是在纳粹压力下被迫关闭的
- **Relationships**: 纳粹接管安哈尔特州 → 德绍关闭 → 柏林废弃工厂 → 盖世太保查封 → 自行解散（order，因果）
- **Composition**: 墨黑暗场，一条从左到右的断裂时间线，四个节点，最后一节点用朱红
- **Title**: 1933：被迫落幕
- **Core message**: 从德绍被关到柏林自行解散，最后的包豪斯只撑了约十个月
- **Content**: 1932 纳粹党接管安哈尔特州政府，德绍校区关闭 · 1932 密斯在柏林租下废弃电话工厂续办约十个月 · 1933.4 盖世太保搜查查封 · 1933.7 密斯与教员投票自行解散
- **Motion suggestion**: 节点按时间依次出现，最后一节点强调
- **Fact IDs**: F017, F018

#### Slide 12 - 流散

- **Audience move**: 以为包豪斯随关闭消失 → 看到师生把方法带到了美国、以色列与战后德国
- **Relationships**: 人物 → 目的地机构（link）；时间先后（order）
- **Composition**: 抽象路线图：左侧德国原点，右侧多个落点（芝加哥、剑桥、黑山、特拉维夫、乌尔姆），白城照片嵌入一个窗口
- **Title**: 关门之后，方法出发
- **Core message**: 关闭让包豪斯的人四散，也让它的方法在新的学校与城市里落地
- **Content**: 阿尔伯斯 1933 → 黑山学院 · 格罗皮乌斯 1937 → 哈佛设计研究生院 · 莫霍利-纳吉 1937 → 芝加哥新包豪斯（1949 并入 IIT）· 密斯 1937/38 → 阿穆尔理工（后 IIT）· 特拉维夫白城 4,000 余座建筑，2003 世界遗产 · 1953 乌尔姆设计学院 / 119 名教员中约 15 人 1933–1938 年移居国外
- **Images**: tel_aviv_white_city.jpg
- **Motion suggestion**: 路线从原点依次射出
- **Fact IDs**: F020, F021, F022, F023, F024, F025, F026

#### Slide 13 - 结语

- **Audience move**: 记住若干事实 → 带走一个判断：包豪斯留下的是方法而非风格
- **Relationships**: 14 年 / 1,250 余名学生 / 29 个国家 / 世界遗产（membership，作为证据支撑结论）
- **Composition**: 一枚朱红大圆回到画面，中心为结论句；下方一排证据数字
- **Title**: 留下的是方法，不是风格
- **Core message**: 基础课 + 工坊 + 工业，这套方法比任何一件作品都走得更远
- **Content**: 结论句 · 14 年 · 1,250 余名学生，来自 29 个国家 · 1996 年魏玛与德绍遗址列入世界遗产，2017 年扩展
- **Closing impact**: 结论 =“留下的是方法，不是风格”；构图为 Reference
- **Motion suggestion**: 承接 P12 的原点圆（Morph 候选）
- **Fact IDs**: F019, F027

## X. Speaker Notes Requirements

- **Generation**: enabled
- **Filename**: match each SVG filename under `notes/`
- **Content**: 以页面为准展开讲解与过渡；只用研究文件中有 fact_id 的事实，冲突处（伊顿离任时间、学生人数口径）按研究文件说明表述
- **Total duration**: 约 25 分钟
- **Notes style**: conversational，叙事+讲解
- **Presentation purpose**: 解释包豪斯的时间线、方法、作品与流散，让听众带走“方法而非风格”的判断
