# Haipo
# BLDC Controller Systematic Learning Knowledge Base

[English](#english) | [中文](#中文)

<a id="english"></a>

## English

This project is a systematic learning knowledge base and online website for engineers developing BLDC and PMSM motor controllers.

Rather than merely collecting links, the project organizes knowledge scattered across motor-control theory, MCU manuals, power-electronics design, embedded software architecture, model-based development, functional safety, calibration, and verification. Its purpose is to help engineers build an end-to-end understanding that can be applied to real controller development.

## Project Goals

- Systematically explain BLDC/PMSM fundamentals and engineering implementation.
- Connect system requirements, hardware, BSW/CDD, application software, and verification.
- Turn fragmented technical material into structured, searchable, maintainable documents.
- Provide organized access to official manuals, application notes, examples, and learning resources.
- Help engineers progress from understanding individual algorithms to developing complete controllers.
- Accumulate reusable templates, review checklists, debugging methods, and verification practices.

## Intended Audience

- BLDC/PMSM motor-control learners
- Motor-control algorithm and Simulink/MBD engineers
- Automotive embedded, BSW, CDD, and AUTOSAR engineers
- MCU driver and real-time software engineers
- Power-electronics and controller hardware engineers
- System requirements, functional safety, diagnostics, and test engineers
- Technical leads who need an end-to-end view of controller development

## Knowledge Architecture

```text
Vehicle, actuator, and stakeholder needs
    |
System boundary, operating scenarios, and requirements
    |
Controller system architecture
    |
    +-- Motor electromagnetics and mechanical load
    +-- Power supply, inverter, and gate driver
    +-- Current, voltage, temperature, and position sensing
    +-- MCU, PWM, ADC, DMA, and communication peripherals
    +-- BSW, CDD, AUTOSAR, and real-time software
    +-- Six-step commutation, sinusoidal control, and FOC
    +-- Simulink models and ASW code generation
    +-- Functional safety, diagnostics, and fault management
    |
MIL / SIL / PIL / HIL / power bench / EMC / environmental and durability validation
```

## Main Learning Areas

### 1. System and Requirements Engineering

- System boundaries, stakeholders, and operating scenarios
- Decomposition of customer specifications into verifiable requirements
- Allocation to hardware, BSW, CDD, ASW, safety, and verification
- Interface control documents, requirement templates, and review checklists
- Bidirectional traceability from source requirements to test evidence

### 2. Motor-Control Algorithms

- BLDC/PMSM electromagnetic and mechanical fundamentals
- Six-step commutation, Hall interpolation, and sinusoidal control
- Clarke/Park transforms, SVPWM, and field-oriented control
- Current, speed, and position control loops
- PI tuning, voltage limiting, anti-windup, field weakening, and MTPA
- Parameter identification, sensorless control, and mode transitions

### 3. Hardware and Power Electronics

- Automotive power supplies, reverse polarity, transients, and low-power operation
- Three-phase inverters, MOSFETs, and gate drivers
- Shunt current sensing, analog front ends, and ADC design
- Hall, encoder, resolver, and sensor interfaces
- Loss calculation, thermal design, EMC, and PCB layout
- Hardware overcurrent protection, short-circuit protection, and independent shutdown

### 4. MCU and Low-Level Software

- Infineon AURIX TC3xx/TC33x architecture
- GTM, EVADC, DMA, MCMCAN, SMU, and watchdogs
- Hardware-synchronized PWM and ADC acquisition
- Interrupts, tasks, memory, and timing budgets
- iLLD, MCAL, CDD, and AUTOSAR layering

### 5. ASW and Model-Based Development

- Discrete and multirate Simulink modeling
- Control algorithms, state machines, and fault strategies
- Data dictionaries, calibration parameters, and interfaces
- Embedded Coder code generation
- Modeling guidelines, reviews, and integration boundaries

### 6. Debugging, Calibration, and Verification

- Identification of motor R, L, Ke, flux linkage, pole pairs, and inertia
- Oscilloscope debugging of PWM, ADC, Hall signals, and control ISRs
- MIL, SIL, PIL, HIL, and power-bench testing
- Current, speed, and position loop calibration
- Fault injection, thermal derating, stall handling, and safe-state verification
- EMC, electrical, environmental, durability, and vehicle validation

## Project Characteristics

- **Systematic:** organized around the complete controller development lifecycle.
- **Engineering-oriented:** connects theory with interfaces, timing, resources, faults, and acceptance criteria.
- **Traceable:** links requirements, architecture, hardware, software, models, and tests.
- **Searchable:** provides a learning website for quickly finding topics and references.
- **Extensible:** supports additional MCU topics, algorithm courses, and practical projects.
- **Source-conscious:** prioritizes official materials from semiconductor vendors, tool vendors, and standards organizations.

## Online Learning Website

GitHub Pages:

[https://mullerhaipo-max.github.io/Haipo/](https://mullerhaipo-max.github.io/Haipo/)

Local website:

```text
ACU_Knowledge_Base/site/index.html
```

## Repository Structure

```text
ACU_Knowledge_Base/
├─ 00_导航与学习路线
├─ 01_系统与需求工程
├─ 02_电机与控制算法
├─ 03_硬件与功率电子
├─ 04_MCU与Infineon_AURIX_TC3xx
├─ 05_BSW_CDD_AUTOSAR
├─ 06_ASW_Simulink_MBD
├─ 07_功能安全与诊断
├─ 08_通信与诊断协议
├─ 09_验证与测试
├─ 10_参考资料索引
└─ site
```

## Local Updates and Publishing

The website is generated from Markdown files under `ACU_Knowledge_Base`.

Build the complete local website:

```powershell
python .\scripts\build_knowledge_site.py
```

Build the public-safe website without local PDFs, ZIP files, or internal project assets:

```powershell
python .\scripts\build_knowledge_site.py --public --output .\public_site
```

Commit and publish after the local repository is connected:

```powershell
.\publish_site.ps1 -Message "Add motor-control learning content"
```

A push to `main` triggers GitHub Actions to rebuild and deploy GitHub Pages.

## Contributing

Recommended structure for a new learning document:

1. Learning objectives
2. Fundamental principles
3. System or software architecture
4. Engineering implementation
5. Common problems and risks
6. Experiments or verification
7. Official learning resources
8. Chapter acceptance criteria

Before publishing, confirm that terminology and units are defined, sources are linked, copyrighted documents are not reproduced, and no confidential customer or project information is included.

## Public Information Boundary

The public website publishes learning articles, website code, and links to public resources. It does not publish customer specifications, internal design baselines, local PDFs, source archives, project identifiers, or confidential parameters.

This knowledge base supports learning and engineering work. Product development must still follow approved project requirements, component data sheets, silicon errata, safety plans, and verification specifications.

---

<a id="中文"></a>

## 中文

本项目是一个面向 BLDC/PMSM 控制器开发工程师的系统化学习知识库和在线学习网站。

项目的目标不是简单收集资料，而是围绕一款 BLDC 控制器从需求到量产验证的完整开发过程，对分散在芯片手册、控制理论、硬件设计、软件架构、模型开发和测试规范中的知识进行分类、梳理和关联，帮助工程师建立可以用于实际项目开发的知识体系。

## 项目目标

- 系统学习 BLDC/PMSM 电机控制的基础理论和工程实现。
- 梳理系统需求、硬件、底层软件、应用软件和验证之间的关系。
- 将零散的技术资料整理成结构化、可查询、可持续更新的学习文档。
- 提供官方手册、应用笔记、代码示例和学习资料的统一入口。
- 帮助工程师从“理解单个算法”逐步走向“具备完整控制器开发能力”。
- 沉淀开发模板、设计检查表、调试方法和验证流程，辅助真实项目开发。

## 适用人群

- BLDC/PMSM 电机控制初学者
- 电机控制算法与 Simulink/MBD 工程师
- 汽车电子嵌入式软件、BSW 和 CDD 工程师
- MCU 底层驱动和 AUTOSAR 工程师
- 功率电子与控制器硬件工程师
- 系统需求、功能安全、诊断和测试工程师
- 希望了解完整控制器开发流程的项目负责人

## 知识体系

```text
车辆、执行器与客户需求
    |
系统边界、运行场景与系统需求
    |
控制器系统架构
    |
    +-- 电机、电磁与机械负载
    +-- 功率电源、逆变桥与门极驱动
    +-- 电流、电压、温度与位置采样
    +-- MCU、PWM、ADC、DMA与通信外设
    +-- BSW、CDD、AUTOSAR与实时软件
    +-- 六步换相、正弦控制与FOC
    +-- Simulink模型与ASW代码生成
    +-- 功能安全、诊断与故障管理
    |
MIL / SIL / PIL / HIL / 功率台架 / EMC / 环境与耐久验证
```

## 主要学习内容

### 1. 系统需求工程

- 系统边界、利益相关方和运行场景
- 客户规范到可验证系统需求的分解
- HW、BSW、CDD、ASW 和 Safety 的需求分配
- 接口控制文档、需求模板和评审清单
- 需求到设计、代码、模型和测试的双向追踪

### 2. 电机与控制算法

- BLDC/PMSM 电磁与机械基础
- 六步换相、Hall 插值和正弦控制
- Clarke/Park 变换、SVPWM 和 FOC
- 电流环、速度环和位置环
- PI 调参、限幅、Anti-windup、弱磁和 MTPA
- 电机参数辨识、无感控制和控制模式切换

### 3. 硬件与功率电子

- 车辆电源、反接、浪涌和低功耗
- 三相逆变桥、MOSFET 和门极驱动
- Shunt 电流采样、模拟前端和 ADC
- Hall、Encoder、Resolver 和传感器接口
- 功率损耗、热设计、EMC 和 PCB 布局
- 硬件过流、短路和独立安全关断

### 4. MCU 与底层软件

- Infineon AURIX TC3xx/TC33x 架构
- GTM、EVADC、DMA、MCMCAN、SMU 和 Watchdog
- PWM 与 ADC 硬件同步
- 中断、任务、存储和时间预算
- iLLD、MCAL、CDD 和 AUTOSAR 分层

### 5. ASW 与模型开发

- Simulink 离散建模和多速率设计
- 控制算法、状态机和故障策略
- 数据字典、标定参数和接口设计
- Embedded Coder 代码生成
- 模型规范、代码审查和集成边界

### 6. 调试、标定与验证

- 电机 R、L、Ke、磁链、极对数和惯量辨识
- PWM、ADC、Hall 和控制 ISR 的示波器调试
- MIL、SIL、PIL、HIL 和功率台架
- 电流环、速度环和位置环调参
- 故障注入、热降额、堵转和安全状态验证
- EMC、环境、电气负载、耐久和车辆验证

## 知识库特点

- **系统化**：按照控制器完整开发生命周期组织内容。
- **工程化**：不仅解释原理，也关注接口、时序、资源、故障和验收。
- **可追踪**：建立需求、架构、软件、硬件和测试之间的联系。
- **可查询**：通过学习网站快速搜索章节、关键词和资料。
- **可扩展**：后续可以持续增加芯片专题、算法课程和项目实践。
- **重视一手资料**：优先整理芯片厂商、工具厂商和标准组织的官方文档。

## 在线学习网站

GitHub Pages：

[https://mullerhaipo-max.github.io/Haipo/](https://mullerhaipo-max.github.io/Haipo/)

本地网站：

```text
ACU_Knowledge_Base/site/index.html
```

## 本地更新与发布

网站由 `ACU_Knowledge_Base` 中的 Markdown 自动生成。

构建本地完整版：

```powershell
python .\scripts\build_knowledge_site.py
```

构建不包含本地 PDF、ZIP 和内部项目资料的公开版本：

```powershell
python .\scripts\build_knowledge_site.py --public --output .\public_site
```

连接本地 GitHub 仓库后，一键提交和发布：

```powershell
.\publish_site.ps1 -Message "补充电机控制学习内容"
```

推送到 `main` 后，GitHub Actions 会自动重新生成和部署网站。

## 如何贡献

建议新增文档按照以下结构组织：

1. 学习目标
2. 基本原理
3. 系统或软件架构
4. 工程实现方法
5. 常见问题和风险
6. 实验或验证步骤
7. 官方学习资料
8. 本章验收标准

发布前应确认术语、单位和引用来源明确，不复制受版权保护的完整文档，也不包含客户名称、项目代号、未公开参数或其他保密信息。

## 公开资料边界

公开网站只发布学习文章、网站代码和公开资料链接，不上传客户原始规范、内部设计基线、本地 PDF、源码压缩包、项目标识或保密参数。

本知识库用于学习和工程辅助。具体产品开发仍应以项目批准的需求、芯片数据手册、器件勘误、功能安全计划和验证规范为准。
# BLDC Controller Systematic Learning Knowledge Base

[English](#english) | [中文](#中文)

<a id="english"></a>

## English

This project is a systematic learning knowledge base and online website for engineers developing BLDC and PMSM motor controllers.

Rather than merely collecting links, the project organizes knowledge scattered across motor-control theory, MCU manuals, power-electronics design, embedded software architecture, model-based development, functional safety, calibration, and verification. Its purpose is to help engineers build an end-to-end understanding that can be applied to real controller development.

## Project Goals

- Systematically explain BLDC/PMSM fundamentals and engineering implementation.
- Connect system requirements, hardware, BSW/CDD, application software, and verification.
- Turn fragmented technical material into structured, searchable, maintainable documents.
- Provide organized access to official manuals, application notes, examples, and learning resources.
- Help engineers progress from understanding individual algorithms to developing complete controllers.
- Accumulate reusable templates, review checklists, debugging methods, and verification practices.

## Intended Audience

- BLDC/PMSM motor-control learners
- Motor-control algorithm and Simulink/MBD engineers
- Automotive embedded, BSW, CDD, and AUTOSAR engineers
- MCU driver and real-time software engineers
- Power-electronics and controller hardware engineers
- System requirements, functional safety, diagnostics, and test engineers
- Technical leads who need an end-to-end view of controller development

## Knowledge Architecture

```text
Vehicle, actuator, and stakeholder needs
    |
System boundary, operating scenarios, and requirements
    |
Controller system architecture
    |
    +-- Motor electromagnetics and mechanical load
    +-- Power supply, inverter, and gate driver
    +-- Current, voltage, temperature, and position sensing
    +-- MCU, PWM, ADC, DMA, and communication peripherals
    +-- BSW, CDD, AUTOSAR, and real-time software
    +-- Six-step commutation, sinusoidal control, and FOC
    +-- Simulink models and ASW code generation
    +-- Functional safety, diagnostics, and fault management
    |
MIL / SIL / PIL / HIL / power bench / EMC / environmental and durability validation
```

## Main Learning Areas

### 1. System and Requirements Engineering

- System boundaries, stakeholders, and operating scenarios
- Decomposition of customer specifications into verifiable requirements
- Allocation to hardware, BSW, CDD, ASW, safety, and verification
- Interface control documents, requirement templates, and review checklists
- Bidirectional traceability from source requirements to test evidence

### 2. Motor-Control Algorithms

- BLDC/PMSM electromagnetic and mechanical fundamentals
- Six-step commutation, Hall interpolation, and sinusoidal control
- Clarke/Park transforms, SVPWM, and field-oriented control
- Current, speed, and position control loops
- PI tuning, voltage limiting, anti-windup, field weakening, and MTPA
- Parameter identification, sensorless control, and mode transitions

### 3. Hardware and Power Electronics

- Automotive power supplies, reverse polarity, transients, and low-power operation
- Three-phase inverters, MOSFETs, and gate drivers
- Shunt current sensing, analog front ends, and ADC design
- Hall, encoder, resolver, and sensor interfaces
- Loss calculation, thermal design, EMC, and PCB layout
- Hardware overcurrent protection, short-circuit protection, and independent shutdown

### 4. MCU and Low-Level Software

- Infineon AURIX TC3xx/TC33x architecture
- GTM, EVADC, DMA, MCMCAN, SMU, and watchdogs
- Hardware-synchronized PWM and ADC acquisition
- Interrupts, tasks, memory, and timing budgets
- iLLD, MCAL, CDD, and AUTOSAR layering

### 5. ASW and Model-Based Development

- Discrete and multirate Simulink modeling
- Control algorithms, state machines, and fault strategies
- Data dictionaries, calibration parameters, and interfaces
- Embedded Coder code generation
- Modeling guidelines, reviews, and integration boundaries

### 6. Debugging, Calibration, and Verification

- Identification of motor R, L, Ke, flux linkage, pole pairs, and inertia
- Oscilloscope debugging of PWM, ADC, Hall signals, and control ISRs
- MIL, SIL, PIL, HIL, and power-bench testing
- Current, speed, and position loop calibration
- Fault injection, thermal derating, stall handling, and safe-state verification
- EMC, electrical, environmental, durability, and vehicle validation

## Project Characteristics

- **Systematic:** organized around the complete controller development lifecycle.
- **Engineering-oriented:** connects theory with interfaces, timing, resources, faults, and acceptance criteria.
- **Traceable:** links requirements, architecture, hardware, software, models, and tests.
- **Searchable:** provides a learning website for quickly finding topics and references.
- **Extensible:** supports additional MCU topics, algorithm courses, and practical projects.
- **Source-conscious:** prioritizes official materials from semiconductor vendors, tool vendors, and standards organizations.

## Online Learning Website

GitHub Pages:

[https://mullerhaipo-max.github.io/Haipo/](https://mullerhaipo-max.github.io/Haipo/)

Local website:

```text
ACU_Knowledge_Base/site/index.html
```

## Repository Structure

```text
ACU_Knowledge_Base/
├─ 00_导航与学习路线
├─ 01_系统与需求工程
├─ 02_电机与控制算法
├─ 03_硬件与功率电子
├─ 04_MCU与Infineon_AURIX_TC3xx
├─ 05_BSW_CDD_AUTOSAR
├─ 06_ASW_Simulink_MBD
├─ 07_功能安全与诊断
├─ 08_通信与诊断协议
├─ 09_验证与测试
├─ 10_参考资料索引
└─ site
```

## Local Updates and Publishing

The website is generated from Markdown files under `ACU_Knowledge_Base`.

Build the complete local website:

```powershell
python .\scripts\build_knowledge_site.py
```

Build the public-safe website without local PDFs, ZIP files, or internal project assets:

```powershell
python .\scripts\build_knowledge_site.py --public --output .\public_site
```

Commit and publish after the local repository is connected:

```powershell
.\publish_site.ps1 -Message "Add motor-control learning content"
```

A push to `main` triggers GitHub Actions to rebuild and deploy GitHub Pages.

## Contributing

Recommended structure for a new learning document:

1. Learning objectives
2. Fundamental principles
3. System or software architecture
4. Engineering implementation
5. Common problems and risks
6. Experiments or verification
7. Official learning resources
8. Chapter acceptance criteria

Before publishing, confirm that terminology and units are defined, sources are linked, copyrighted documents are not reproduced, and no confidential customer or project information is included.

## Public Information Boundary

The public website publishes learning articles, website code, and links to public resources. It does not publish customer specifications, internal design baselines, local PDFs, source archives, project identifiers, or confidential parameters.

This knowledge base supports learning and engineering work. Product development must still follow approved project requirements, component data sheets, silicon errata, safety plans, and verification specifications.

---

<a id="中文"></a>

## 中文

本项目是一个面向 BLDC/PMSM 控制器开发工程师的系统化学习知识库和在线学习网站。

项目的目标不是简单收集资料，而是围绕一款 BLDC 控制器从需求到量产验证的完整开发过程，对分散在芯片手册、控制理论、硬件设计、软件架构、模型开发和测试规范中的知识进行分类、梳理和关联，帮助工程师建立可以用于实际项目开发的知识体系。

## 项目目标

- 系统学习 BLDC/PMSM 电机控制的基础理论和工程实现。
- 梳理系统需求、硬件、底层软件、应用软件和验证之间的关系。
- 将零散的技术资料整理成结构化、可查询、可持续更新的学习文档。
- 提供官方手册、应用笔记、代码示例和学习资料的统一入口。
- 帮助工程师从“理解单个算法”逐步走向“具备完整控制器开发能力”。
- 沉淀开发模板、设计检查表、调试方法和验证流程，辅助真实项目开发。

## 适用人群

- BLDC/PMSM 电机控制初学者
- 电机控制算法与 Simulink/MBD 工程师
- 汽车电子嵌入式软件、BSW 和 CDD 工程师
- MCU 底层驱动和 AUTOSAR 工程师
- 功率电子与控制器硬件工程师
- 系统需求、功能安全、诊断和测试工程师
- 希望了解完整控制器开发流程的项目负责人

## 知识体系

```text
车辆、执行器与客户需求
    |
系统边界、运行场景与系统需求
    |
控制器系统架构
    |
    +-- 电机、电磁与机械负载
    +-- 功率电源、逆变桥与门极驱动
    +-- 电流、电压、温度与位置采样
    +-- MCU、PWM、ADC、DMA与通信外设
    +-- BSW、CDD、AUTOSAR与实时软件
    +-- 六步换相、正弦控制与FOC
    +-- Simulink模型与ASW代码生成
    +-- 功能安全、诊断与故障管理
    |
MIL / SIL / PIL / HIL / 功率台架 / EMC / 环境与耐久验证
```

## 主要学习内容

### 1. 系统需求工程

- 系统边界、利益相关方和运行场景
- 客户规范到可验证系统需求的分解
- HW、BSW、CDD、ASW 和 Safety 的需求分配
- 接口控制文档、需求模板和评审清单
- 需求到设计、代码、模型和测试的双向追踪

### 2. 电机与控制算法

- BLDC/PMSM 电磁与机械基础
- 六步换相、Hall 插值和正弦控制
- Clarke/Park 变换、SVPWM 和 FOC
- 电流环、速度环和位置环
- PI 调参、限幅、Anti-windup、弱磁和 MTPA
- 电机参数辨识、无感控制和控制模式切换

### 3. 硬件与功率电子

- 车辆电源、反接、浪涌和低功耗
- 三相逆变桥、MOSFET 和门极驱动
- Shunt 电流采样、模拟前端和 ADC
- Hall、Encoder、Resolver 和传感器接口
- 功率损耗、热设计、EMC 和 PCB 布局
- 硬件过流、短路和独立安全关断

### 4. MCU 与底层软件

- Infineon AURIX TC3xx/TC33x 架构
- GTM、EVADC、DMA、MCMCAN、SMU 和 Watchdog
- PWM 与 ADC 硬件同步
- 中断、任务、存储和时间预算
- iLLD、MCAL、CDD 和 AUTOSAR 分层

### 5. ASW 与模型开发

- Simulink 离散建模和多速率设计
- 控制算法、状态机和故障策略
- 数据字典、标定参数和接口设计
- Embedded Coder 代码生成
- 模型规范、代码审查和集成边界

### 6. 调试、标定与验证

- 电机 R、L、Ke、磁链、极对数和惯量辨识
- PWM、ADC、Hall 和控制 ISR 的示波器调试
- MIL、SIL、PIL、HIL 和功率台架
- 电流环、速度环和位置环调参
- 故障注入、热降额、堵转和安全状态验证
- EMC、环境、电气负载、耐久和车辆验证

## 知识库特点

- **系统化**：按照控制器完整开发生命周期组织内容。
- **工程化**：不仅解释原理，也关注接口、时序、资源、故障和验收。
- **可追踪**：建立需求、架构、软件、硬件和测试之间的联系。
- **可查询**：通过学习网站快速搜索章节、关键词和资料。
- **可扩展**：后续可以持续增加芯片专题、算法课程和项目实践。
- **重视一手资料**：优先整理芯片厂商、工具厂商和标准组织的官方文档。

## 在线学习网站

GitHub Pages：

[https://mullerhaipo-max.github.io/Haipo/](https://mullerhaipo-max.github.io/Haipo/)

本地网站：

```text
ACU_Knowledge_Base/site/index.html
```

## 本地更新与发布

网站由 `ACU_Knowledge_Base` 中的 Markdown 自动生成。

构建本地完整版：

```powershell
python .\scripts\build_knowledge_site.py
```

构建不包含本地 PDF、ZIP 和内部项目资料的公开版本：

```powershell
python .\scripts\build_knowledge_site.py --public --output .\public_site
```

连接本地 GitHub 仓库后，一键提交和发布：

```powershell
.\publish_site.ps1 -Message "补充电机控制学习内容"
```

推送到 `main` 后，GitHub Actions 会自动重新生成和部署网站。

## 如何贡献

建议新增文档按照以下结构组织：

1. 学习目标
2. 基本原理
3. 系统或软件架构
4. 工程实现方法
5. 常见问题和风险
6. 实验或验证步骤
7. 官方学习资料
8. 本章验收标准

发布前应确认术语、单位和引用来源明确，不复制受版权保护的完整文档，也不包含客户名称、项目代号、未公开参数或其他保密信息。

## 公开资料边界

公开网站只发布学习文章、网站代码和公开资料链接，不上传客户原始规范、内部设计基线、本地 PDF、源码压缩包、项目标识或保密参数。

本知识库用于学习和工程辅助。具体产品开发仍应以项目批准的需求、芯片数据手册、器件勘误、功能安全计划和验证规范为准。

