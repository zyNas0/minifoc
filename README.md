<!--
 * @Author: yang zhang 
 * @Date: 2025-08-11 09:44:16
 * @LastEditors: yang zhang
 * @LastEditTime: 2026-04-08 17:17:53
 * @FilePath: \minifoc\README.md
 * @Description: 
 * 
 * 
 * Copyright (c) 2026 by , All Rights Reserved. 
-->
# simpleFOC

一个使用 USB PD 供电的简易 FOC 驱动项目。

## 项目简介

本项目面向无刷电机控制学习与原型验证，核心目标是基于 STM32 平台实现一套可运行、可调试、可扩展的简易 FOC 驱动系统。

项目重点：

1. 使用 USB PD 作为主供电输入，满足便携与桌面调试场景。
2. 完成电机基础驱动链路，包括外设初始化、PWM 输出、采样与控制闭环基础框架。
3. 提供 Keil 与 CMake 双工程形态，便于快速开发与后续工程化。

## 当前范围

当前仓库内容主要覆盖：

1. 底层外设驱动与工程模板（GPIO、SPI、I2C、TIM、USART、ADC 等）。
2. LCD、编码器等基础 BSP 模块。
3. 硬件资料与 3D 结构文件，便于联调与机械集成。

## 硬件与软件环境

硬件侧：

1. STM32H743VI 系列主控。
2. FOC 驱动板与配套无刷电机。
3. AS5600 等位置传感器模块。
4. USB PD 供电链路。

软件侧：

1. Keil MDK 工程：用于常规下载调试。
2. CMake 工程：用于跨工具链构建与持续集成。
3. Ozone/J-Link：用于在线调试与分析。

## 目录说明

1. SDK：主开发目录，包含 STM32 工程源码、BSP、驱动与工程配置。
2. HDK：硬件相关资料，包括说明书、3D 模型与参考资源。
3. build：CMake 构建产物目录。

## 快速开始

1. 准备硬件并确认供电链路稳定，建议先在限流条件下上电。
2. 根据开发习惯选择 Keil 或 CMake 工程编译。
3. 下载固件后先验证基础外设，再逐步联调电机控制链路。
4. 需要清理 Keil 中间文件时，可使用 SDK/keilclean.bat。

## 后续计划

1. 补充更完整的 FOC 控制参数说明与调参建议。
2. 增加电机启动、闭环控制与异常保护相关示例。
3. 完善调试记录与常见问题清单。

## 注意事项

1. 在使用Ozone时加载.axf文件时需要选择 Read from Base Address Vector Table ，而不能选择ELF Entry Point。
