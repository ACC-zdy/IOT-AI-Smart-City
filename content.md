# 面向高密度城市数字孪生的 Urban AIoT 感知系统研究框架

**Urban AIoT for High-Density City Digital Twins**

## 0. 总体定位

本研究框架以 **城市物联网 Urban IoT / 城市智能物联网 Urban AIoT** 为主体，面向高密度城市中的微气候、空气质量、洪水韧性、噪声、交通舒适度、建筑能源与城市安全等复杂治理问题，构建由 **电子传感硬件、低功耗通信网络、边缘智能、可信数据空间、三维城市数字孪生与城市治理应用** 组成的系统性研究路线。

澳门大学智慧城市物联网国家重点实验室的学科布局可作为邻近参照：其研究重点包括 **智能感知与网络通信、城市大数据与智能技术、智慧能源、智能交通、城市安全与灾害防治**，与本框架中的 Urban AIoT 研究结构高度一致。([skliotsc.um.edu.mo][1])

**核心技术链条：**
城市传感硬件 → 固定/移动 IoT 网络 → 边缘 AI 质控与推理 → 可信城市数据空间 → 三维/环境/交通/洪水/能源数字孪生 → 城市治理决策支持。

**涉及的电子/IoT/AI 技术：**
电子与硬件：传感器节点、MCU、RISC-V、FPGA、STM32、低功耗电路、电源管理、传感器标定、户外封装。
物联网与系统：LoRaWAN、NB-IoT、5G、MQTT、边缘网关、设备管理、OTA 更新、实时数据流、时空数据库。
AI 与数字孪生：边缘推理、TinyML、异常检测、传感器校准、时空预测、多源融合、3DGS/点云重建、城市仿真、可信数据共享。

**参考入口：**
State Key Laboratory of Internet of Things for Smart City, University of Macau
URL: [https://skliotsc.um.edu.mo/about/lab-introduction/](https://skliotsc.um.edu.mo/about/lab-introduction/)
URL: [https://skliotsc.um.edu.mo/research/](https://skliotsc.um.edu.mo/research/)

---

# A. 城市 IoT 感知基础设施

**Urban IoT Sensing Infrastructure**

## A1. 固定式低成本城市环境传感网络

**Fixed Low-Cost Urban Environmental Sensor Networks**

### 研究对象

固定式城市环境传感网络旨在通过低成本、低功耗、可长期维护的传感节点，在街区、道路、校园、社区、公园、巴士站、灯杆、建筑外立面等城市空间中连续采集环境数据。典型监测对象包括空气温度、湿度、热岛强度、PM2.5/PM10、NO₂/O₃、噪声、水位、雨量、光照、辐射、风速等。

### 研究意义

传统气象站或空气质量监测站数量有限，难以捕捉高密度城市中街谷、建筑遮阴、地表材料、交通排放、海风与坡地共同作用下的超局地差异。低成本固定传感网络能够为城市微气候、空气污染暴露、热风险识别和城市韧性规划提供高时空分辨率数据。UCL LoRaWAN 热环境传感器研究即以低功耗传感系统解决城市温湿度数据稀缺问题，并将数据与 GIS 结合服务城市热岛政策分析。

### 对应电子/IoT/AI 技术

电子技术：温湿度传感器、气体传感器、颗粒物传感器、声学传感器、水位传感器、MCU、低功耗电源管理、电池/太阳能供电、户外防水封装、传感器标定。
IoT 技术：LoRaWAN、The Things Network、NB-IoT、MQTT、设备注册、节点定位、时间同步、远程诊断、OTA 固件更新、网关部署。
AI 技术：传感器漂移检测、异常数据剔除、低成本传感器校准、空间插值、热区识别、时空预测、不确定性估计。

### 代表项目/文献

Array of Things / Waggle, Chicago
说明：开放智能传感与边缘计算平台，用于城市环境、基础设施与活动数据的实时采集。
URL: [https://arrayofthings.github.io/](https://arrayofthings.github.io/)
URL: [https://wa8.gl/](https://wa8.gl/)

Dongyi Ma et al., “Using Bespoke LoRaWAN Heat Sensors to Explore Microclimate Effects within the London Urban Heat Islands”
说明：低成本、轻量、电池供电 LoRaWAN 热环境传感器，用于伦敦东区微气候与城市热岛研究。
URL: [https://discovery.ucl.ac.uk/id/eprint/10194007/](https://discovery.ucl.ac.uk/id/eprint/10194007/)

Dongyi Ma et al., “Open-Source LoRaWAN Sensors for Distributed IoT Networks: Crowdsourced Environmental Data Collection for Climate Resilient Cities”
说明：开源 LoRaWAN 传感器、PCB、3D 打印外壳与公民科学部署，用于构建伦敦级微气候网络。
URL: [https://discovery.ucl.ac.uk/id/eprint/10224163/](https://discovery.ucl.ac.uk/id/eprint/10224163/)

SPTel LoRaWAN Sensor Network, Singapore
说明：新加坡面向 Smart Nation 的低功耗广域传感网络，支持水位、洪水、空气质量、街灯、垃圾、害虫等应用。
URL: [https://sptel.com/first-sensor-network/](https://sptel.com/first-sensor-network/)

Seoul S-DoT, Smart Seoul Data of Things
说明：首尔城市 IoT 传感基础设施，用于颗粒物、人口、噪声、光照等城市数据采集与政策支持。
URL: [https://english.seoul.go.kr/policy/smart-city/iot-communications-security/](https://english.seoul.go.kr/policy/smart-city/iot-communications-security/)

---

## A2. 移动式城市感知网络

**Mobile Urban Sensing Networks**

### 研究对象

移动式城市感知网络通过公交、小巴、出租车、物流车、骑行设备、步行背包、手机外挂传感器等移动载体采集街道级环境数据。相比固定节点，移动节点能够利用城市交通网络补足空间覆盖不足，并以更低成本生成高分辨率暴露地图。

### 研究意义

高密度城市中的空气污染、热暴露和噪声水平在几十米尺度内即可发生显著变化，单靠固定站点难以形成街道级风险认知。移动感知可以形成沿道路、街谷、人行路径和交通廊道展开的动态监测体系。MIT Flatburn / City Scanner 展示了开源低成本移动空气污染传感器的技术路线，并强调移动低成本传感器必须处理天气影响、漂移、老化和校准问题。

### 对应电子/IoT/AI 技术

电子技术：车载传感器盒、PM/NO₂/O₃/CO₂ 传感器、温湿度传感器、地表温度传感器、GPS、IMU、蓝牙模块、车载电源、抗震封装。
IoT 技术：手机网关、车载网关、Bluetooth、LTE/5G、移动数据上传、轨迹同步、map matching、固定—移动混合网络。
AI 技术：移动传感器校准、轨迹覆盖优化、污染暴露建模、热暴露建模、传感器漂移补偿、空间随机性建模、时空融合、domain adaptation。

### 代表项目/文献

MIT Senseable City Lab, Flatburn / City Scanner
说明：开源、低成本、可车载的移动空气污染检测器，支持 3D 打印与低成本部件制作，并已与高精度设备对比校准。
URL: [https://news.mit.edu/2023/low-cost-device-can-measure-air-pollution-anywhere-0316](https://news.mit.edu/2023/low-cost-device-can-measure-air-pollution-anywhere-0316)
URL: [https://senseable.mit.edu/flatburn/](https://senseable.mit.edu/flatburn/)

Wang et al., “Leveraging Machine Learning Algorithms to Advance Low-Cost Air Sensor Calibration in Stationary and Mobile Settings”
说明：面向固定与移动低成本空气质量传感器的机器学习校准研究。
URL: [https://www.sciencedirect.com/science/article/pii/S1352231023000633](https://www.sciencedirect.com/science/article/pii/S1352231023000633)

HKU / ECF Project, “A Low-cost Mobile Sensing Platform for Air Quality Monitoring at High Spatial Resolution in Hong Kong”
说明：面向香港高密度城市空气质量的低成本移动感知平台，关注空间随机性、测量不确定性、map matching、传感器校准、固定—移动融合等问题。
URL: [https://www.ecf.gov.hk/doc/research_project_summary2023-138.pdf](https://www.ecf.gov.hk/doc/research_project_summary2023-138.pdf)

Cho et al., Android-based low-cost mobile thermal environment sensing platform
说明：集成温度、地表温度、湿度、气压、光照、加速度等多模态数据，支持步行、滑板车、电动自行车等移动采集。
URL: [https://zenodo.org/records/8343053](https://zenodo.org/records/8343053)

---

## A3. 公民科学与众包感知

**Citizen Sensing and Participatory Urban IoT**

### 研究对象

公民科学与众包感知强调将低成本传感器从实验室和政府项目扩散到社区、学校、居民、NGO 和公众组织中，通过开源硬件、标准化部署方法和开放数据平台形成参与式城市环境监测网络。

### 研究意义

城市环境风险具有明显的空间不平等特征。社区参与式传感能够增强公众对热风险、空气污染、噪声暴露和环境正义问题的感知，同时扩大城市传感网络覆盖范围。UCL 2025 年开源 LoRaWAN 传感器工作明确提出通过开源原理图、PCB 文件和 3D 打印外壳支持社区构建传感器，推动众包气候数据采集。

### 对应电子/IoT/AI 技术

电子技术：开源 PCB、低成本 BOM、模块化传感器、3D 打印外壳、低维护电源、易安装结构。
IoT 技术：节点注册、开放 API、社区数据平台、设备身份管理、数据许可、众包数据上传。
AI 技术：众包数据质量控制、异常设备检测、多设备一致性校准、可信度评分、参与式数据可视化。

### 代表项目/文献

Dongyi Ma et al., Open-Source LoRaWAN Sensors for Distributed IoT Networks
URL: [https://discovery.ucl.ac.uk/id/eprint/10224163/](https://discovery.ucl.ac.uk/id/eprint/10224163/)

MIT Flatburn / City Scanner
URL: [https://news.mit.edu/2023/low-cost-device-can-measure-air-pollution-anywhere-0316](https://news.mit.edu/2023/low-cost-device-can-measure-air-pollution-anywhere-0316)
URL: [https://senseable.mit.edu/flatburn/](https://senseable.mit.edu/flatburn/)

Public Lab, Community Science and Environmental Monitoring
说明：面向公众参与环境监测的开源社区科学平台。
URL: [https://publiclab.org/](https://publiclab.org/)

---

# B. 边缘智能与硬件系统

**Edge Intelligence and Device-Level AIoT Systems**

## B1. 软件定义传感器与边缘 AI 节点

**Software-Defined Sensors and Edge AI Nodes**

### 研究对象

软件定义传感器不再只是被动采集数据，而是在传感节点本地集成计算能力，支持边缘推理、数据筛选、事件检测、模型更新、隐私保护和任务重配置。SAGE/Waggle 将传感器节点设计为可运行边缘 AI 的开放平台，可连接相机、LiDAR、空气质量、风速和 LoRaWAN 低带宽传感器，并在嵌入式计算机上运行机器学习模型。

### 对应电子/IoT/AI 技术

电子技术：Jetson、Raspberry Pi、RISC-V、STM32、ESP32、RGB/红外相机、LiDAR、气体传感器、风传感器、边缘算力模块。
IoT 技术：软件定义传感节点、容器化边缘应用、边缘—云协同、远程应用下发、节点健康监测、设备任务调度。
AI 技术：本地目标检测、异常检测、边缘数据压缩、事件触发采样、视觉隐私保护、多模态融合、在线模型更新。

### 代表项目/文献

SAGE: A Software-Defined Sensor Network
URL: [https://sagecontinuum.org/](https://sagecontinuum.org/)
URL: [https://sagecontinuum.org/docs/about/overview](https://sagecontinuum.org/docs/about/overview)

Waggle Edge Computing Platform
URL: [https://wa8.gl/](https://wa8.gl/)

Array of Things / Waggle
URL: [https://arrayofthings.github.io/](https://arrayofthings.github.io/)

---

## B2. TinyML / RISC-V / 低功耗边缘推理

**TinyML and RISC-V Edge Intelligence for Urban IoT**

### 研究对象

该方向关注在资源受限的 IoT 节点上部署轻量 AI 模型，使城市传感器具备本地推理能力。典型任务包括异常检测、传感器漂移预警、短期环境预测、低功耗事件识别和数据压缩。

### 对应电子/IoT/AI 技术

电子技术：RISC-V MCU、ARM Cortex-M、GAP-8、PULP-NN、低功耗神经网络加速、片上 SRAM/Flash 约束、电源管理。
IoT 技术：LoRa/NB-IoT 低带宽通信、边缘模型部署、OTA 模型更新、边缘聚合节点、设备端模型版本管理。
AI 技术：TinyML、模型量化、剪枝、TCN、1D CNN、异常检测、联邦学习、通信压缩、能耗感知推理。

### 代表项目/文献

PULP Platform / GAP-8 / PULP-NN
说明：面向超低功耗并行 RISC-V 处理器的嵌入式神经网络推理生态。
URL: [https://pulp-platform.org/](https://pulp-platform.org/)
URL: [https://github.com/pulp-platform/pulp-nn](https://github.com/pulp-platform/pulp-nn)

Federated Learning and TinyML on IoT Edge Devices: Challenges, Advancements, and Future Directions
说明：综述 FL、TinyML 与 IoT 边缘设备结合中的通信、隐私、准确率、能耗和内存限制。
URL: [https://nchr.elsevierpure.com/en/publications/federated-learning-and-tinyml-on-iot-edge-devices-challenges-adva/](https://nchr.elsevierpure.com/en/publications/federated-learning-and-tinyml-on-iot-edge-devices-challenges-adva/)

TinyML Foundation
URL: [https://www.tinyml.org/](https://www.tinyml.org/)

---

## B3. 低成本传感器校准、漂移与不确定性建模

**Calibration, Drift Compensation, and Uncertainty Modeling**

### 研究对象

低成本传感器的大规模部署必须处理温湿度干扰、交叉敏感性、设备老化、漂移、批次差异和场景迁移等问题。该方向是从“可采集数据”走向“可用于政策与治理数据”的关键。

### 对应电子/IoT/AI 技术

电子技术：传感器实验标定、参考仪器共址实验、温湿度补偿、电化学传感器响应建模。
IoT 技术：固定—移动联合校准、设备健康状态监测、校准参数远程更新、参考站数据融合。
AI 技术：机器学习校准、domain adaptation、uncertainty-aware mapping、漂移检测、贝叶斯校准、数据质量评分。

### 代表项目/文献

Wang et al., “Leveraging Machine Learning Algorithms to Advance Low-Cost Air Sensor Calibration in Stationary and Mobile Settings”
URL: [https://www.sciencedirect.com/science/article/pii/S1352231023000633](https://www.sciencedirect.com/science/article/pii/S1352231023000633)

MIT Flatburn / City Scanner calibration discussion
URL: [https://news.mit.edu/2023/low-cost-device-can-measure-air-pollution-anywhere-0316](https://news.mit.edu/2023/low-cost-device-can-measure-air-pollution-anywhere-0316)

Ma et al., LoRaWAN heat sensor deployment and validation
URL: [https://discovery.ucl.ac.uk/id/eprint/10194007/](https://discovery.ucl.ac.uk/id/eprint/10194007/)

---

## B4. 隐私保护边缘感知

**Privacy-Preserving Edge Sensing**

### 研究对象

城市 IoT 系统中，视觉、声音、轨迹和人流数据往往涉及隐私风险。隐私保护边缘感知要求在节点本地完成目标计数、事件检测、视觉摘要或数据匿名化，避免上传可识别的原始数据。

### 对应电子/IoT/AI 技术

电子技术：本地摄像头模组、音频传感器、边缘计算芯片、可信执行环境。
IoT 技术：数据最小化、边缘匿名化、加密传输、设备身份认证、访问控制。
AI 技术：本地目标检测、人流计数、车流计数、语音/噪声特征提取、图像脱敏、联邦学习、差分隐私。

### 代表项目/文献

Array of Things Privacy Policy and Edge Processing
URL: [https://arrayofthings.github.io/policies.html](https://arrayofthings.github.io/policies.html)

Waggle / SAGE edge AI platform
URL: [https://wa8.gl/](https://wa8.gl/)
URL: [https://sagecontinuum.org/](https://sagecontinuum.org/)

---

# C. 城市数字孪生与数据平台

**Urban Digital Twin and Data Platform**

## C1. 实时城市数字孪生平台

**Real-Time Urban Digital Twins**

### 研究对象

实时城市数字孪生平台将城市三维模型、传感器流数据、交通数据、环境数据、人口活动数据和仿真模型融合，用于城市规划、灾害响应、环境治理和政策推演。Virtual Singapore 是典型案例，其目标是构建数据丰富的 3D 新加坡模型，并接入实时传感数据支持城市模拟。

### 对应电子/IoT/AI 技术

电子技术：城市环境传感器、交通传感器、摄像头、建筑设备传感器。
IoT 技术：实时数据接入、流数据管道、时空数据库、设备 API、传感器—三维对象绑定。
AI 技术：城市状态估计、异常检测、场景预测、仿真校准、多源时空融合。

### 代表项目/文献

Virtual Singapore, GovTech Singapore
URL: [https://www.tech.gov.sg/technews/5-things-to-know-about-virtual-singapore/](https://www.tech.gov.sg/technews/5-things-to-know-about-virtual-singapore/)

Virtual Singapore, Dassault Systèmes case study
URL: [https://www.3ds.com/insights/customer-stories/virtual-singapore](https://www.3ds.com/insights/customer-stories/virtual-singapore)

---

## C2. 城市操作系统、IoT 中间件与平台互操作

**Urban Operating Systems, IoT Middleware, and Interoperability**

### 研究对象

城市级 IoT 系统需要连接不同厂商、不同协议、不同部门和不同数据格式的传感设备与运营系统。城市中间件和开放数字平台的研究重点在于实现数据集成、流程自动化、跨系统互操作和实时决策支持。Singapore Open Digital Platform 即强调 operational technology systems 的互操作、数据集成、流程自动化和实时决策。

### 对应电子/IoT/AI 技术

电子技术：多厂商传感器接入、边缘网关、协议适配器。
IoT 技术：MQTT、Kafka、REST API、设备管理平台、数据流处理、IoT middleware、跨平台互操作。
AI 技术：规则引擎、事件检测、自动告警、实时决策支持、任务调度优化。

### 代表项目/文献

Singapore Open Digital Platform
URL: [https://www.developer.tech.gov.sg/products/categories/sensor-platforms-and-internet-of-things/open-digital-platform/overview](https://www.developer.tech.gov.sg/products/categories/sensor-platforms-and-internet-of-things/open-digital-platform/overview)

Open Digital Platform Features and Roadmap
URL: [https://www.developer.tech.gov.sg/products/categories/sensor-platforms-and-internet-of-things/open-digital-platform/features-roadmap](https://www.developer.tech.gov.sg/products/categories/sensor-platforms-and-internet-of-things/open-digital-platform/features-roadmap)

---

## C3. 城市气候与环境数字孪生

**Urban Climate and Environmental Digital Twins**

### 研究对象

城市气候数字孪生将城市环境传感数据、微气候模型、建筑能耗模型、交通模型、地表模型和区域气候模型融合，用于城市热岛、户外热舒适、气候韧性和降温策略评估。Cooling Singapore 2.0 的 DUCT 目标是构建 Digital Urban Climate Twin，整合环境、地表、工业、交通、建筑能耗和区域/微尺度气候模型。

### 对应电子/IoT/AI 技术

电子技术：温湿度、风速、辐射、黑球温度、空气质量、建筑能耗传感器。
IoT 技术：城市气候传感网络、实时气象接入、环境数据平台、模型数据接口。
AI 技术：微气候预测、热风险识别、降温策略模拟、模型校准、物理模型与数据驱动模型融合。

### 代表项目/文献

Cooling Singapore / Digital Urban Climate Twin, Singapore-ETH Centre
URL: [https://sec.ethz.ch/research/cs/About.html](https://sec.ethz.ch/research/cs/About.html)

Cooling Singapore, Centre for Liveable Cities
URL: [https://knowledgehub.clc.gov.sg/liveability-in-action/box-story--cooling-singapore/](https://knowledgehub.clc.gov.sg/liveability-in-action/box-story--cooling-singapore/)

URA Singapore, Heat Resilient City / DUCT
URL: [https://www.ura.gov.sg/Corporate/Get-Involved/Plan-Our-Future-SG/Innovative-Urban-Solutions/Heat-resilient-city](https://www.ura.gov.sg/Corporate/Get-Involved/Plan-Our-Future-SG/Innovative-Urban-Solutions/Heat-resilient-city)

---

## C4. 可信城市数据空间与数据主权

**Trusted Urban Data Spaces and Data Sovereignty**

### 研究对象

城市 IoT 数据通常跨越政府部门、研究机构、企业、交通运营方、环保组织和公众社区，涉及数据权限、隐私、安全、可信共享和合规使用。可信城市数据空间研究关注数据连接器、身份认证、访问控制、使用策略、审计和跨主体协同。

Gaia-X 强调安全、透明、可控的数据主权和互操作，IDS Connector 则提供数据空间中连接既有系统与数据资源的技术入口。

### 对应电子/IoT/AI 技术

电子技术：可信设备身份、硬件根信任、TEE、ARM TrustZone、Intel SGX、设备证书。
IoT 技术：数据连接器、身份管理、访问控制、数据目录、审计日志、跨部门数据共享。
AI 技术：联邦学习、隐私保护分析、可信 AI、数据质量评分、异常访问检测、可解释数据治理。

### 代表项目/文献

Gaia-X: A Federated Secure Data Infrastructure
URL: [https://gaia-x.eu/](https://gaia-x.eu/)

Gaia-X, What is Gaia-X
URL: [https://gaia-x.eu/what-is-gaia-x/](https://gaia-x.eu/what-is-gaia-x/)

International Data Spaces Association, Data Connector
URL: [https://international-data-spaces-association.github.io/DataspaceConnector/Introduction](https://international-data-spaces-association.github.io/DataspaceConnector/Introduction)

IDS Knowledge Base, Connector
URL: [https://kb.internationaldataspaces.org/ids-knowledgebase/idsa-rulebook/functional-requirements/125_connector/](https://kb.internationaldataspaces.org/ids-knowledgebase/idsa-rulebook/functional-requirements/125_connector/)

---

# D. 三维城市几何与环境数字孪生

**3D Geometry-Enhanced Urban AIoT and Environmental Digital Twins**

## D1. 三维几何增强的热舒适建模

**3D Geometry-Enhanced Outdoor Thermal Comfort Modeling**

### 研究对象

该方向将三维城市几何、点云、街景影像、3DGS、DSM、建筑形态、植被结构与热环境传感数据结合，用于街道尺度的平均辐射温度 Tmrt、热舒适、阴影、天空可视因子和热暴露建模。

SOLWEIG/UMEP 是关键参考，其功能包括在复杂城市环境中估计 3D 辐射通量和平均辐射温度，并需要空气温度、相对湿度、城市几何、地理位置、植被和地表等输入。

### 对应电子/IoT/AI 技术

电子技术：街道热环境传感器、辐射传感器、移动测温设备、全景相机、LiDAR、GNSS/IMU。
IoT 技术：固定节点与移动节点融合、三维城市模型更新、街道级热舒适图层、传感器—几何对象关联。
AI 技术：3DGS、点云重建、天空可视因子估计、阴影分析、几何—热环境融合、MRT/UTCI 预测、模型校准。

### 代表项目/文献

UMEP / SOLWEIG Manual
URL: [https://umep-docs.readthedocs.io/en/latest/OtherManuals/SOLWEIG.html](https://umep-docs.readthedocs.io/en/latest/OtherManuals/SOLWEIG.html)

UMEP SOLWEIG Tutorial
URL: [https://umep-docs.readthedocs.io/projects/tutorial/en/latest/Tutorials/IntroductionToSolweig.html](https://umep-docs.readthedocs.io/projects/tutorial/en/latest/Tutorials/IntroductionToSolweig.html)

Lindberg et al., SOLWEIG 1.0 – Modelling spatial variations of 3D radiant fluxes and mean radiant temperature in complex urban settings
URL: [https://link.springer.com/article/10.1007/s00484-008-0162-7](https://link.springer.com/article/10.1007/s00484-008-0162-7)

Cooling Singapore / DUCT
URL: [https://sec.ethz.ch/research/cs/About.html](https://sec.ethz.ch/research/cs/About.html)

---

## D2. 三维城市几何与空气质量、通风、街谷暴露

**3D Urban Morphology for Air Quality, Ventilation, and Exposure**

### 研究对象

街谷形态、建筑高度、道路宽度、植被遮挡、天空可视因子和交通排放共同决定了局地空气污染和通风条件。三维几何增强的空气质量研究将移动/固定传感器数据与街道几何结合，用于解释污染热点、暴露差异和通风不足区域。

### 对应电子/IoT/AI 技术

电子技术：空气质量传感器、车载传感器、全景相机、LiDAR、GNSS/IMU。
IoT 技术：移动空气质量采样、道路级数据绑定、街道对象级数据管理、固定—移动数据融合。
AI 技术：街谷几何特征提取、污染热点预测、通风潜力建模、图神经网络、空间回归、时空融合。

### 代表项目/文献

HKU / ECF Low-cost Mobile Sensing Platform for Air Quality Monitoring in Hong Kong
URL: [https://www.ecf.gov.hk/doc/research_project_summary2023-138.pdf](https://www.ecf.gov.hk/doc/research_project_summary2023-138.pdf)

MIT Flatburn / City Scanner
URL: [https://news.mit.edu/2023/low-cost-device-can-measure-air-pollution-anywhere-0316](https://news.mit.edu/2023/low-cost-device-can-measure-air-pollution-anywhere-0316)

Virtual Singapore
URL: [https://www.tech.gov.sg/technews/5-things-to-know-about-virtual-singapore/](https://www.tech.gov.sg/technews/5-things-to-know-about-virtual-singapore/)

---

## D3. 全球/区域气候数字孪生到街道尺度

**From Global and Regional Climate Twins to Street-Level Urban Action**

### 研究对象

该方向关注将全球或区域气候模拟、城市级气候模型、街道级传感网络和三维城市模型连接起来，实现从宏观气候风险到微观街道干预的尺度转换。NVIDIA Earth-2 展示了将高分辨率气候模拟数据与 3D 地图和可视化结合，并将城市尺度模拟纳入地球数字孪生的路径。

### 对应电子/IoT/AI 技术

电子技术：本地气象和环境传感网络，用于模型校正与验证。
IoT 技术：城市观测流、气象 API、边缘—云协同、模型数据接口。
AI 技术：天气 AI、气候降尺度、物理模型与数据驱动模型融合、城市风险预测、情景推演。

### 代表项目/文献

NVIDIA Earth-2
URL: [https://www.nvidia.com/en-us/high-performance-computing/earth-2/](https://www.nvidia.com/en-us/high-performance-computing/earth-2/)

Destination Earth, European Commission
URL: [https://destination-earth.eu/](https://destination-earth.eu/)

Cooling Singapore / Digital Urban Climate Twin
URL: [https://sec.ethz.ch/research/cs/About.html](https://sec.ethz.ch/research/cs/About.html)

---

# E. 城市治理应用方向

**Urban Governance and Resilience Applications**

## E1. 微气候、城市热岛与热舒适治理

**Urban Microclimate, Heat Island, and Thermal Comfort Governance**

### 研究对象

该方向关注城市热岛、街道热暴露、户外热舒适、绿地冷却效应、遮阴设施、冷屋顶、街区形态和热风险人群保护。高密度、高湿、高楼街谷城市尤其需要超局地热环境监测和基于数字孪生的干预评估。

### 对应电子/IoT/AI 技术

电子技术：温湿度、风速、辐射、黑球温度、地表温度传感器。
IoT 技术：LoRaWAN 热环境节点、移动热环境采样、城市热风险实时地图。
AI 技术：热岛预测、热舒适指数估计、冷却策略模拟、绿地冷却评估、风险人群暴露建模。

### 代表项目/文献

UCL LoRaWAN Heat Sensors, London
URL: [https://discovery.ucl.ac.uk/id/eprint/10194007/](https://discovery.ucl.ac.uk/id/eprint/10194007/)

UCL Open-Source LoRaWAN Sensors, DCOSS-IoT 2025
URL: [https://discovery.ucl.ac.uk/id/eprint/10224163/](https://discovery.ucl.ac.uk/id/eprint/10224163/)

Cooling Singapore / DUCT
URL: [https://sec.ethz.ch/research/cs/About.html](https://sec.ethz.ch/research/cs/About.html)

UMEP / SOLWEIG
URL: [https://umep-docs.readthedocs.io/en/latest/OtherManuals/SOLWEIG.html](https://umep-docs.readthedocs.io/en/latest/OtherManuals/SOLWEIG.html)

---

## E2. 空气质量与街道暴露评估

**Air Quality and Street-Level Exposure Assessment**

### 研究对象

该方向聚焦街道级空气污染监测、人群暴露评估、移动传感器校准、固定—移动传感融合、污染热点识别和高风险路径分析。香港等高密度城市中，路边排放、街谷通风和人群活动高度耦合，适合形成具有本地特色的研究问题。

### 对应电子/IoT/AI 技术

电子技术：PM2.5/PM10、NO₂、O₃、CO₂、温湿度、GPS、IMU、车载供电。
IoT 技术：车载移动节点、实时上传、轨迹 map matching、固定站融合、街道级污染图层。
AI 技术：低成本空气传感器校准、污染暴露建模、轨迹补全、空间插值、不确定性地图、时空预测。

### 代表项目/文献

HKU / ECF Low-cost Mobile Sensing Platform for Air Quality Monitoring in Hong Kong
URL: [https://www.ecf.gov.hk/doc/research_project_summary2023-138.pdf](https://www.ecf.gov.hk/doc/research_project_summary2023-138.pdf)

MIT Flatburn / City Scanner
URL: [https://news.mit.edu/2023/low-cost-device-can-measure-air-pollution-anywhere-0316](https://news.mit.edu/2023/low-cost-device-can-measure-air-pollution-anywhere-0316)

Wang et al., Low-cost air sensor calibration in stationary and mobile settings
URL: [https://www.sciencedirect.com/science/article/pii/S1352231023000633](https://www.sciencedirect.com/science/article/pii/S1352231023000633)

---

## E3. 洪水、积涝与城市灾害韧性

**Urban Flooding, Pluvial Risk, and Disaster Resilience**

### 研究对象

该方向面向暴雨、城市积水、水位异常、排水系统超载、地下空间风险和应急路径规划，构建低成本水文传感网络与洪水数字孪生系统。城市洪水数字孪生通常融合 IoT、遥感、AI、机器学习和水文模型，用于实时监测、预警和防灾决策。

### 对应电子/IoT/AI 技术

电子技术：超声波水位传感器、雨量计、流量计、土壤湿度传感器、防水边缘节点、低功耗供电。
IoT 技术：水位实时上传、低功耗广域通信、排水系统数据接入、灾害事件流、预警平台。
AI 技术：降雨—积涝预测、洪水风险图、传感器异常检测、物理模型校正、应急路径规划、灾害响应优化。

### 代表项目/文献

Urban Flood Digital Twin Review, Remote Sensing 2025
URL: [https://www.mdpi.com/2072-4292/17/17/3104](https://www.mdpi.com/2072-4292/17/17/3104)

NCKU Digital Twin Urban Flood Forecasting System
URL: [https://researchoutput.ncku.edu.tw/en/publications/a-digital-twin-urban-flood-forecasting-system-integrating-a-weath/](https://researchoutput.ncku.edu.tw/en/publications/a-digital-twin-urban-flood-forecasting-system-integrating-a-weath/)

Real-Time Urban Flood Monitoring IoT Research
URL: [https://repository.uwl.ac.uk/id/eprint/12017/](https://repository.uwl.ac.uk/id/eprint/12017/)

---

## E4. 噪声、施工与交通舒适度

**Urban Noise, Construction Noise, and Traffic Comfort**

### 研究对象

该方向关注道路交通噪声、施工噪声、居民暴露、工人暴露、声环境地图和交通舒适度。DTU 的 Construction Noise Digital Twin 将 BIM 中的噪声源信息与现场实时传感数据结合，用于生成动态噪声地图，并支持施工设备任务分配、场地布局和工期优化。

### 对应电子/IoT/AI 技术

电子技术：分贝计、麦克风阵列、声学传感节点、施工设备定位、边缘音频采样。
IoT 技术：现场噪声传感网络、BIM 数据接入、实时噪声地图、事件告警、施工流程数据集成。
AI 技术：噪声源识别、声场预测、时空插值、异常噪声检测、施工计划优化、交通舒适度建模。

### 代表项目/文献

DTU, Digital Twin for Control of Noise Emissions from Heavy Equipment on Construction Sites
URL: [https://orbit.dtu.dk/en/publications/digital-twin-for-control-of-noise-emissions-from-heavy-equipment-/](https://orbit.dtu.dk/en/publications/digital-twin-for-control-of-noise-emissions-from-heavy-equipment-/)

DTU, Predictive Simulation of Construction Site Noise Emissions
URL: [https://orbit.dtu.dk/en/publications/predictive-simulation-of-construction-site-noise-emissions-from-h/](https://orbit.dtu.dk/en/publications/predictive-simulation-of-construction-site-noise-emissions-from-h/)

Urban Noise Monitoring with Wireless Sensor Networks
URL: [https://www.mdpi.com/1424-8220/18/12/4366](https://www.mdpi.com/1424-8220/18/12/4366)

---

## E5. 建筑能源、室内外舒适度与低碳街区

**Building Energy, Indoor–Outdoor Comfort, and Low-Carbon Districts**

### 研究对象

该方向关注建筑能耗、HVAC 控制、室内外热环境联动、占用行为、楼宇自动化系统和低碳街区管理。建筑能源数字孪生通常将 BIM、IoT 传感器、建筑自动化系统和 AI 控制结合，用于能耗预测、舒适度控制与运维优化。

### 对应电子/IoT/AI 技术

电子技术：室内温湿度、CO₂、占用传感器、电表、空调状态传感器、楼宇控制接口。
IoT 技术：BMS/BAS 接入、建筑传感网络、室内外环境数据融合、建筑—街区数据平台。
AI 技术：能耗预测、占用行为学习、HVAC 优化控制、异常能耗检测、舒适度—节能多目标优化。

### 代表项目/文献

Building Digital Twin Review, Applied Sciences
URL: [https://www.mdpi.com/2076-3417/15/19/10795](https://www.mdpi.com/2076-3417/15/19/10795)

AI-Enhanced Building Digital Twins Review
URL: [https://orca.cardiff.ac.uk/id/eprint/180509/](https://orca.cardiff.ac.uk/id/eprint/180509/)

Cooling Singapore / Building Energy and Urban Climate Integration
URL: [https://sec.ethz.ch/research/cs/About.html](https://sec.ethz.ch/research/cs/About.html)

---

## E6. 多要素城市韧性融合

**Multi-Hazard and Multi-Factor Urban Resilience**

### 研究对象

多要素城市韧性研究将热、空气污染、洪水、噪声、交通、能源和人群暴露综合建模，形成面向城市更新、老旧街区治理、公共健康和气候适应的综合风险评估框架。

### 对应电子/IoT/AI 技术

电子技术：多模态环境传感节点、复合传感器盒、移动采样设备。
IoT 技术：多源数据接入、跨系统互操作、城市数据湖、实时风险图层。
AI 技术：多模态融合、图神经网络、时空预测、多风险叠加评估、城市干预策略优化。

### 代表项目/文献

Virtual Singapore
URL: [https://www.tech.gov.sg/technews/5-things-to-know-about-virtual-singapore/](https://www.tech.gov.sg/technews/5-things-to-know-about-virtual-singapore/)

Open Digital Platform, Singapore
URL: [https://www.developer.tech.gov.sg/products/categories/sensor-platforms-and-internet-of-things/open-digital-platform/overview](https://www.developer.tech.gov.sg/products/categories/sensor-platforms-and-internet-of-things/open-digital-platform/overview)

NVIDIA Earth-2
URL: [https://www.nvidia.com/en-us/high-performance-computing/earth-2/](https://www.nvidia.com/en-us/high-performance-computing/earth-2/)

Cooling Singapore / DUCT
URL: [https://sec.ethz.ch/research/cs/About.html](https://sec.ethz.ch/research/cs/About.html)

---

# F. 研究主线凝练

**Integrated Research Trajectory**

## F1. 总体研究主题

**Hardware-Enabled Urban AIoT and Digital Twins for High-Density City Resilience**
**面向高密度城市韧性治理的硬件使能 Urban AIoT 与数字孪生系统**

## F2. 系统结构

低成本多源传感节点
→ 固定/移动混合 IoT 网络
→ 边缘 AI 质控、校准与推理
→ 可信城市数据空间
→ 三维城市几何与环境数字孪生
→ 城市微气候、空气质量、洪水、噪声、能源与交通舒适度治理。

## F3. 核心研究支线

### 支线一：高密度城市街道级环境 AIoT 网络

研究重点：固定节点、移动节点和社区节点构成的低成本城市环境感知网络。
技术重点：传感器硬件、LoRaWAN/NB-IoT、移动网关、传感器校准、时空数据融合。
代表参考：UCL LoRaWAN Heat Sensors、MIT Flatburn、Seoul S-DoT、HKU ECF Mobile Sensing。

参考链接：
URL: [https://discovery.ucl.ac.uk/id/eprint/10194007/](https://discovery.ucl.ac.uk/id/eprint/10194007/)
URL: [https://discovery.ucl.ac.uk/id/eprint/10224163/](https://discovery.ucl.ac.uk/id/eprint/10224163/)
URL: [https://news.mit.edu/2023/low-cost-device-can-measure-air-pollution-anywhere-0316](https://news.mit.edu/2023/low-cost-device-can-measure-air-pollution-anywhere-0316)
URL: [https://www.ecf.gov.hk/doc/research_project_summary2023-138.pdf](https://www.ecf.gov.hk/doc/research_project_summary2023-138.pdf)
URL: [https://english.seoul.go.kr/policy/smart-city/iot-communications-security/](https://english.seoul.go.kr/policy/smart-city/iot-communications-security/)

### 支线二：边缘智能城市传感节点

研究重点：RISC-V/TinyML/软件定义传感器在城市 IoT 节点中的部署。
技术重点：低功耗推理、边缘异常检测、模型量化、OTA 模型更新、隐私保护边缘计算。
代表参考：SAGE/Waggle、PULP-NN、TinyML。

参考链接：
URL: [https://sagecontinuum.org/](https://sagecontinuum.org/)
URL: [https://wa8.gl/](https://wa8.gl/)
URL: [https://pulp-platform.org/](https://pulp-platform.org/)
URL: [https://github.com/pulp-platform/pulp-nn](https://github.com/pulp-platform/pulp-nn)
URL: [https://www.tinyml.org/](https://www.tinyml.org/)

### 支线三：三维几何增强的城市热环境数字孪生

研究重点：3DGS/点云/街景几何与 IoT 热环境传感数据融合，服务热舒适和城市热岛治理。
技术重点：3DGS、点云重建、SOLWEIG/UMEP、MRT/Tmrt、UTCI、阴影分析、天空可视因子估计。
代表参考：Cooling Singapore、UMEP/SOLWEIG、Virtual Singapore。

参考链接：
URL: [https://sec.ethz.ch/research/cs/About.html](https://sec.ethz.ch/research/cs/About.html)
URL: [https://umep-docs.readthedocs.io/en/latest/OtherManuals/SOLWEIG.html](https://umep-docs.readthedocs.io/en/latest/OtherManuals/SOLWEIG.html)
URL: [https://www.tech.gov.sg/technews/5-things-to-know-about-virtual-singapore/](https://www.tech.gov.sg/technews/5-things-to-know-about-virtual-singapore/)

### 支线四：可信城市 IoT 数据空间与平台互操作

研究重点：跨部门、跨平台、跨设备的城市 IoT 数据可信共享与协同治理。
技术重点：Data Connector、身份认证、访问控制、TEE、数据主权、联邦学习、审计。
代表参考：Gaia-X、International Data Spaces、Singapore Open Digital Platform。

参考链接：
URL: [https://gaia-x.eu/](https://gaia-x.eu/)
URL: [https://international-data-spaces-association.github.io/DataspaceConnector/Introduction](https://international-data-spaces-association.github.io/DataspaceConnector/Introduction)
URL: [https://www.developer.tech.gov.sg/products/categories/sensor-platforms-and-internet-of-things/open-digital-platform/overview](https://www.developer.tech.gov.sg/products/categories/sensor-platforms-and-internet-of-things/open-digital-platform/overview)
