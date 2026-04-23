<div class="markdown"><h1>Proclaw-Scam-insight.skil | 骗局洞察者.skill</h1>
<h2>任务目标</h2>
<ul>
<li>本 Skill 用于：识别金融骗局模式、分析收割机制的本质结构、提供反收割决策框架</li>
<li>能力包含：底层公理理解、骗局系统拆解、风险结构分析、反收割策略执行</li>
<li>触发条件：用户询问投资是否靠谱、分析某项目是否骗局、学习如何避免被收割、理解骗局背后的机制</li>
</ul>
<h2>前置准备</h2>
<ul>
<li>依赖说明：
<ul>
<li>python: pandas==2.0.0, numpy==1.24.0, matplotlib==3.7.0</li>
</ul>
</li>
<li>认知准备：接受"不确定性是底层常量"这一核心公理</li>
</ul>
<h2>操作步骤</h2>
<h3>标准流程</h3>
<h4>步骤1：识别需求缺口（最隐蔽但最致命）</h4>
<p>判断对方是否在制造"需求缺口"：</p>
<ul>
<li>是否在放大你对不确定性的恐惧？（银行不安全、通胀、错过机会）</li>
<li>是否在制造焦虑？（不投就后悔、机会流失）</li>
<li>是否在暗示"你是少数幸运儿"？</li>
</ul>
<p>如果存在以上信号，说明你被当作"韭菜"定位了。</p>
<h4>步骤2：分析确定性叙事（核心判断点）</h4>
<p>对方提供的"确定性解决方案"是否包含以下关键词：</p>
<ul>
<li>"稳定收益" "年化固定" "保本" "可预测"</li>
<li>"低风险高回报" "内部渠道" "专家背书"</li>
<li>"不用懂""跟着就行""别人已经赚了"</li>
</ul>
<p>只要出现这些词，<strong>已经违背金融本质</strong>。</p>
<h4>步骤3：拆解风险结构（必须回答五个问题）</h4>
<p>对于任何投资机会，你必须强制自己回答：</p>
<ol>
<li><strong>收益从哪里来？</strong>（是谁亏的钱？还是透支未来？）</li>
<li><strong>风险在哪里？</strong>（识别被包装、被隐藏的部分）</li>
<li><strong>谁在承担风险？</strong>（如果你不知道，那一定是你）</li>
<li><strong>最坏情况是什么？</strong>（会不会让你出局？）</li>
<li><strong>如果我错了，代价是多少？</strong>（单次错误是否致命？）</li>
</ol>
<p>任何一个问题答不出来，说明你在被利用。</p>
<h4>步骤4：识别收割节点（检查是否进入收割路径）</h4>
<p>对照收割系统的七个节点判断当前状态：</p>
<ul>
<li>节点1：需求缺口是否被制造</li>
<li>节点2：确定性方案是否被提供</li>
<li>节点3：认知门槛是否被降低（"不用懂"）</li>
<li>节点4：信任闭环是否建立（小收益→复利幻觉→加大投入）</li>
<li>节点5：资金是否开始聚集</li>
<li>节点6：风险是否在悄悄转移</li>
<li>节点7：流动性是否濒临断裂</li>
</ul>
<p>如果已经进入节点4-7，说明收割正在发生。</p>
<h4>步骤5：执行反收割决策（基于五个控制变量）</h4>
<p>基于以下五个变量做出决策：</p>
<ol>
<li><strong>不确定性承受能力</strong>：能不能接受波动？不能则不入场</li>
<li><strong>认知深度</strong>：是否看懂了收益来源和风险结构？看不懂则不入局</li>
<li><strong>时间维度</strong>：是短期情绪驱动还是长期结构主导？短期不参与</li>
<li><strong>资金位置</strong>：你赚的是谁的钱？不知道则是对手盘</li>
<li><strong>决策来源</strong>：是自主判断还是接受叙事？后者立即撤退</li>
</ol>
<p>反收割行动：</p>
<ul>
<li>不追求"确定性"，追求"正期望"</li>
<li>不"All in"，控制仓位确保单次错误不出局</li>
<li>不听故事，只看结构和对手盘</li>
<li>不追涨杀跌，反人性执行</li>
</ul>
<h3>量化工具调用</h3>
<h4>凯利公式计算器</h4>
<p><strong>用途</strong>：计算最优投资仓位比例</p>
<p><strong>调用示例</strong>：</p>
<pre><code class="language-bash"># 对称盈亏（胜率60%，盈利100%，亏损100%）
python scripts/kelly_criterion.py --win-rate 0.6 --win-amount 100 --loss-amount 100

# 非对称盈亏（胜率40%，盈利50%，亏损10%）
python scripts/kelly_criterion.py --win-rate 0.4 --win-amount 50 --loss-amount 10 --conservative 0.25
</code></pre>
<h4>风险指标计算器</h4>
<p><strong>用途</strong>：计算夏普比率、最大回撤、VaR、索提诺比率</p>
<p><strong>调用示例</strong>：</p>
<pre><code class="language-bash"># 使用价格序列计算所有指标
python scripts/risk_metrics.py --prices '[100,105,110,108,112,115,113,118]'

# 使用收益率序列计算
python scripts/risk_metrics.py --returns '[0.05,0.0476,-0.0182,0.037,0.0268,-0.0174,0.0442]'
</code></pre>
<h4>骗局风险评分系统</h4>
<p><strong>用途</strong>：计算CRS（骗局风险）、LRS（流动性风险）和综合风险评分</p>
<p><strong>调用示例</strong>：</p>
<pre><code class="language-bash"># 高风险案例
python scripts/scam_risk_scorer.py --revenue-source 0 --risk-identification 0 --cognitive-threshold 0 --liquidity 0 --information 0 --withdrawal-difficulty 0 --lock-period 0 --order-depth 0 --slippage 0

# 中风险案例
python scripts/scam_risk_scorer.py --revenue-source 1 --risk-identification 1 --cognitive-threshold 1 --liquidity 1 --information 1 --withdrawal-difficulty 1 --lock-period 2 --order-depth 2 --slippage 2
</code></pre>
<h4>决策矩阵评估</h4>
<p><strong>用途</strong>：评估骗局风险判断矩阵和投资机会评估矩阵</p>
<p><strong>调用示例</strong>：</p>
<pre><code class="language-bash"># 骗局风险矩阵评估
python scripts/decision_matrix.py --matrix-type scam --scores '{"revenue_source":0,"risk_identification":0,"cognitive_threshold":0,"trust_building":0,"liquidity":0,"information_transparency":0}'

# 投资机会矩阵评估
python scripts/decision_matrix.py --matrix-type investment --scores '{"expected_value":4,"risk_control":3,"liquidity":4,"information_transparency":3,"time_match":4}'
</code></pre>
<h4>流动性分析工具</h4>
<p><strong>用途</strong>：分析订单簿、流动性需求和供给、流动性风险</p>
<p><strong>调用示例</strong>：</p>
<pre><code class="language-bash"># 基本订单簿分析
python scripts/liquidity_analyzer.py --bid-price 10.00 --ask-price 10.05 --bid-volume 10000 --ask-volume 5000

# 完整流动性分析
python scripts/liquidity_analyzer.py --bid-price 10.00 --ask-price 10.05 --bid-volume 10000 --ask-volume 5000 --panic-sell-volume 30000 --normal-volume 5000 --available-funds 10000
</code></pre>
<h4>可视化工具</h4>
<p><strong>用途</strong>：生成风险热力图、骗局网络拓扑图、资金流向追踪图、决策树可视化</p>
<p><strong>调用示例</strong>：</p>
<pre><code class="language-bash"># 风险热力图
python scripts/visualization.py --type risk-heatmap --data '{"risks":{"high":80,"medium":15,"low":5}}' --output risk_heatmap.png

# 网络拓扑图
python scripts/visualization.py --type network-topology --data '{"nodes":["A","B","C","D"],"edges":[["A","B"],["B","C"],["C","D"]]}' --output network_topology.png
</code></pre>
<h4>数据处理工具</h4>
<p><strong>用途</strong>：数据清洗、数据分析、批量评分、报告生成</p>
<p><strong>调用示例</strong>：</p>
<pre><code class="language-bash"># 批量评分
python scripts/data_processor.py --input data.csv --task batch-score --output report.html
</code></pre>
<h3>可选分支</h3>
<ul>
<li><strong>当需要深度理解底层理论</strong>：阅读 <a href="references/underlying-principles.md">references/underlying-principles.md</a>（底层公理与核心轴）</li>
<li><strong>当需要拆解具体骗局系统</strong>：阅读 <a href="references/scam-system-model.md">references/scam-system-model.md</a>（完整收割模型）</li>
<li><strong>当需要构建反收割系统</strong>：阅读 <a href="references/anti-scam-framework.md">references/anti-scam-framework.md</a>（执行框架）</li>
<li><strong>当需要理解规则与定价权</strong>：阅读 <a href="references/power-and-pricing-layer.md">references/power-and-pricing-layer.md</a>（规则设计与定价权）</li>
<li><strong>当需要顶层玩家路径</strong>：阅读 <a href="references/top-player-path.md">references/top-player-path.md</a>（实操与进化）</li>
<li><strong>当需要量化模型与算法</strong>：阅读 <a href="references/quantitative-core.md">references/quantitative-core.md</a>（凯利公式、夏普比率、VaR等）</li>
<li><strong>当需要理解行为心理学</strong>：阅读 <a href="references/behavioral-psychology.md">references/behavioral-psychology.md</a>（损失厌恶、前景理论、锚定效应）</li>
<li><strong>当需要定价与估值</strong>：阅读 <a href="references/pricing-and-valuation.md">references/pricing-and-valuation.md</a>（DCF、相对估值、梅特卡夫定律）</li>
<li><strong>当需要理解流动性危机</strong>：阅读 <a href="references/liquidity-and-crisis.md">references/liquidity-and-crisis.md</a>（订单簿、滑点、崩盘前兆）</li>
<li><strong>当需要决策工具</strong>：阅读 <a href="references/decision-tools.md">references/decision-tools.md</a>（决策树、判断矩阵、检查清单）</li>
<li><strong>当需要识别骗局类型</strong>：阅读 <a href="references/scam-taxonomy.md">references/scam-taxonomy.md</a>（金融/技术/社交/商业骗局完整图谱）</li>
<li><strong>当需要实战案例分析</strong>：阅读 <a href="references/scam-case-studies.md">references/scam-case-studies.md</a>（e租宝、麦道夫、PlusToken等案例拆解）</li>
<li><strong>当需要理解社交工程</strong>：阅读 <a href="references/social-engineering-algorithms.md">references/social-engineering-algorithms.md</a>（信任构建、群体传播、信息操纵）</li>
<li><strong>当需要博弈论应用</strong>：阅读 <a href="references/game-theory-applications.md">references/game-theory-applications.md</a>（纳什均衡、博弈树、多轮博弈）</li>
<li><strong>当需要防御策略</strong>：阅读 <a href="references/defense-strategies.md">references/defense-strategies.md</a>（分类型防御、多层级防御、应急响应）</li>
<li><strong>当需要复杂系统量化</strong>：阅读 <a href="references/complex-systems-quantification.md">references/complex-systems-quantification.md</a>（网络效应、相变点、黑天鹅）</li>
<li><strong>当需要实战演练</strong>：阅读 <a href="references/interactive-training.md">references/interactive-training.md</a>（交互式案例、场景训练、错误分析）</li>
<li><strong>当需要历史演化分析</strong>：阅读 <a href="references/historical-evolution.md">references/historical-evolution.md</a>（从古代到现代的骗局演化）</li>
</ul>
<h2>使用示例</h2>
<h3>示例1：判断"年化8%稳定收益"项目</h3>
<ul>
<li><strong>场景/输入</strong>：有人推荐"年化8%稳定收益，保本保息"</li>
<li><strong>预期产出</strong>：识别这是典型的确定性幻觉骗局</li>
<li><strong>关键要点</strong>：
<ol>
<li>识别叙事关键词："稳定""保本保息" - 违背金融本质</li>
<li>回答五个问题：收益来源？谁承担风险？答不出→骗局</li>
<li>对照收割节点：确定性方案已提供，认知门槛被降低</li>
<li>反收割决策：拒绝，因为追求确定性是被收割的前置条件</li>
</ol>
</li>
</ul>
<h3>示例2：分析某P2P爆雷事件</h3>
<ul>
<li><strong>场景/输入</strong>：用户询问"某某P2P为什么会爆雷？我亏了钱"</li>
<li><strong>预期产出</strong>：拆解完整的收割路径，解释风险转移机制</li>
<li><strong>关键要点</strong>：
<ol>
<li>回溯收割链路：需求缺口（通胀恐惧）→确定性方案（稳定收益）→降低门槛（不用懂）→信任建立（小收益）→资金聚集→风险转移→流动性断裂</li>
<li>分析收益来源：本质上是用新资金兑付旧收益（庞氏结构）</li>
<li>风险转移风险从设计者转移到参与者</li>
<li>真相：用户不是"投资"，而是"买安心感"</li>
</ol>
</li>
</ul>
<h3>示例3：学习反收割策略</h3>
<ul>
<li><strong>场景/输入</strong>：用户表示"我总是被骗，想知道如何避免"</li>
<li><strong>预期产出</strong>：提供五步强制判断流程和四个策略</li>
<li><strong>关键要点</strong>：
<ol>
<li>五步强制判断：每次决策前必须回答五个核心问题</li>
<li>概率思维：不问"能不能赚钱"，问"长期正期望吗"</li>
<li>仓位系统：设计"允许犯错的系统"，单次错误不出局</li>
<li>反叙事能力：问"这个故事如果是假的，骗点在哪里"</li>
<li>进化路径：从"被收割者"→"认知觉醒"→"结构理解"→"策略执行"→"结构利用"</li>
</ol>
</li>
</ul>
<h3>示例4：从防守到进攻（进阶）</h3>
<ul>
<li><strong>场景/输入</strong>：用户表示"我已经能避免被骗了，如何升级到顶层玩家"</li>
<li><strong>预期产出</strong>：提供从参与者到设计者的升级路径</li>
<li><strong>关键要点</strong>：
<ol>
<li>理解定价权：解释权 = 定价权 = 收益分配权</li>
<li>掌握三大权力：定价权、流量控制权、规则定义权</li>
<li>构建信息优势：深度调研、人脉网络、系统化思考</li>
<li>设计规则结构：成为规则的一部分，而不是参与者</li>
<li>升级路径：防守（不被收割）→理解（拆解结构）→进攻（主动设计）</li>
</ol>
</li>
</ul>
<h3>示例5：量化评估投资机会（专业级）</h3>
<ul>
<li><strong>场景/输入</strong>：用户询问"年化30%的项目，值得投吗？"</li>
<li><strong>预期产出</strong>：使用量化模型系统化评估</li>
<li><strong>关键要点</strong>：
<ol>
<li>使用凯利公式脚本计算仓位：<code>python scripts/kelly_criterion.py --win-rate 0.5 --win-amount 3 --loss-amount 1</code></li>
<li>使用风险指标脚本评估风险：<code>python scripts/risk_metrics.py --returns '[0.3,0.25,-0.15,0.35,0.2]'</code></li>
<li>使用骗局风险评分：<code>python scripts/scam_risk_scorer.py --revenue-source 1 --risk-identification 1 ...</code></li>
<li>综合分析量化结果，做出决策</li>
</ol>
</li>
</ul>
<h3>示例6：流动性危机识别（实战级）</h3>
<ul>
<li><strong>场景/输入</strong>：某平台提现困难，用户询问"是否会爆雷？"</li>
<li><strong>预期产出</strong>：使用流动性分析工具评估</li>
<li><strong>关键要点</strong>：
<ol>
<li>使用流动性分析脚本：<code>python scripts/liquidity_analyzer.py --bid-price 10.00 --ask-price 10.50 --bid-volume 1000 --ask-volume 10000 --panic-sell-volume 30000 --normal-volume 5000 --available-funds 5000</code></li>
<li>分析输出中的流动性需求和供给</li>
<li>检查风险警告（critical/severe/moderate）</li>
<li>根据整体风险评级做出决策</li>
</ol>
</li>
</ul>
<h2>资源索引</h2>
<h3>基础理论</h3>
<ul>
<li>参考：见 <a href="references/underlying-principles.md">references/underlying-principles.md</a>（何时读取：需要理解底层公理、核心轴、收益来源时）</li>
<li>参考：见 <a href="references/scam-system-model.md">references/scam-system-model.md</a>（何时读取：需要拆解完整骗局系统、理解收割机制时）</li>
<li>参考：见 <a href="references/behavioral-psychology.md">references/behavioral-psychology.md</a>（何时读取：需要理解人性弱点、骗局心理学时）</li>
</ul>
<h3>反收割框架</h3>
<ul>
<li>参考：见 <a href="references/anti-scam-framework.md">references/anti-scam-framework.md</a>（何时读取：需要构建反收割执行系统、学习具体策略时）</li>
<li>参考：见 <a href="references/decision-tools.md">references/decision-tools.md</a>（何时读取：需要使用决策树、判断矩阵、检查清单时）</li>
</ul>
<h3>进阶能力</h3>
<ul>
<li>参考：见 <a href="references/power-and-pricing-layer.md">references/power-and-pricing-layer.md</a>（何时读取：需要理解规则设计、定价权、从参与者升级到设计者时）</li>
<li>参考：见 <a href="references/top-player-path.md">references/top-player-path.md</a>（何时读取：需要学习策略模型执行、资金配置、信息优势构建、从防守到进攻的完整路径时）</li>
</ul>
<h3>量化模型</h3>
<ul>
<li>参考：见 <a href="references/quantitative-core.md">references/quantitative-core.md</a>（何时读取：需要使用凯利公式、夏普比率、最大回撤、VaR等量化模型时）</li>
<li>参考：见 <a href="references/pricing-and-valuation.md">references/pricing-and-valuation.md</a>（何时读取：需要使用DCF、相对估值、梅特卡夫定律等定价方法时）</li>
<li>参考：见 <a href="references/liquidity-and-crisis.md">references/liquidity-and-crisis.md</a>（何时读取：需要理解流动性危机、订单簿、崩盘前兆时）</li>
</ul>
<h3>脚本工具</h3>
<ul>
<li>脚本：见 <a href="scripts/kelly_criterion.py">scripts/kelly_criterion.py</a>（用途：计算最优投资仓位比例，支持对称和非对称盈亏，提供保守策略建议）</li>
<li>脚本：见 <a href="scripts/risk_metrics.py">scripts/risk_metrics.py</a>（用途：计算夏普比率、最大回撤、VaR、索提诺比率等风险指标）</li>
<li>脚本：见 <a href="scripts/scam_risk_scorer.py">scripts/scam_risk_scorer.py</a>（用途：计算CRS骗局风险评分、LRS流动性风险评分和综合风险评分）</li>
<li>脚本：见 <a href="scripts/decision_matrix.py">scripts/decision_matrix.py</a>（用途：评估骗局风险判断矩阵和投资机会评估矩阵）</li>
<li>脚本：见 <a href="scripts/liquidity_analyzer.py">scripts/liquidity_analyzer.py</a>（用途：分析订单簿、流动性需求和供给、流动性风险）</li>
</ul>
<h3>骗局识别与防御</h3>
<ul>
<li>参考：见 <a href="references/scam-taxonomy.md">references/scam-taxonomy.md</a>（何时读取：需要识别金融/技术/社交/商业等骗局类型、了解骗局特征时）</li>
<li>参考：见 <a href="references/scam-case-studies.md">references/scam-case-studies.md</a>（何时读取：需要学习e租宝、麦道夫、PlusToken等经典骗局案例、理解收割路径时）</li>
<li>参考：见 <a href="references/social-engineering-algorithms.md">references/social-engineering-algorithms.md</a>（何时读取：需要理解信任构建、群体传播、心理操控等社交工程算法时）</li>
<li>参考：见 <a href="references/game-theory-applications.md">references/game-theory-applications.md</a>（何时读取：需要理解纳什均衡、博弈树、多轮博弈等博弈论应用时）</li>
<li>参考：见 <a href="references/defense-strategies.md">references/defense-strategies.md</a>（何时读取：需要学习分类型防御策略、多层级防御体系、应急响应机制时）</li>
</ul>
<h2>注意事项</h2>
<ul>
<li>接受"不确定性"是入场门票，追求"确定性"是进入收割轨道</li>
<li>前期收益不是能力证明，只是"诱饵成本"</li>
<li>不懂的不碰，看不懂的不入，这比亏钱更安全</li>
<li>所有被收割的人，本质是在用钱购买"安心感"</li>
<li>市场只奖励敢面对不确定性且有能力管理它的人</li>
</ul>
<h2>进阶能力</h2>
<p>从防守到进攻的升级路径：</p>
<h3>阶段1：不被收割（防守）</h3>
<ul>
<li>目标：识别骗局，避免被收割</li>
<li>能力：五步判断、概率思维、仓位控制</li>
<li>参考：anti-scam-framework.md</li>
</ul>
<h3>阶段2：理解结构（过渡）</h3>
<ul>
<li>目标：理解市场运行机制，拆解收割系统</li>
<li>能力：系统思维、结构分析、风险识别</li>
<li>参考：underlying-principles.md、scam-system-model.md</li>
</ul>
<h3>阶段3：主动设计（进攻）</h3>
<ul>
<li>目标：掌握定价权，设计规则，控制流量</li>
<li>能力：资源整合、规则设计、影响力</li>
<li>参考：power-and-pricing-layer.md、top-player-path.md</li>
</ul>
<h3>核心升级关键</h3>
<ul>
<li>从"接受规则"到"设计规则"</li>
<li>从"被动反应"到"主动定价"</li>
<li>从"跟随流量"到"控制流量"</li>
</ul></div>
