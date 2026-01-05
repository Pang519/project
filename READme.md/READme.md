# 高速混合訊號系統與 TI-ADC 數位校正專案
# (High-Speed Mixed-Signal System with Digital Calibration for TI-ADC)

## 📌 專案簡介
本專案致力於解決高速通訊系統中 **時間交錯類比數位轉換器 (TI-ADC)** 的物理非理想性問題。透過數位訊號處理 (DSP) 技術，補償通道間的偏移 (Offset)、增益 (Gain) 與時序偏差 (Timing Skew)。

## 🏗️ 系統架構
本專案採軟硬整合架構，實現從物理層到應用層的全鏈路設計：
* **硬體層 (Hardware)**: 使用 LTspice 進行前端電路模擬，確保訊號完整性 (SI/PI)。
* **演算法 (Algorithms)**: 於 MATLAB 建模，實作 LMS 背景校正演算法。
* **實作層 (Implementation)**: 
  - **RTL**: 使用 Verilog 於 FPGA 實現硬體加速邏輯。
  - **Firmware**: 基於 MCU 處理數據擷取與通訊協議。
  - **Software**: Linux 環境下以 C++ 處理數據流，並透過 Flask 提供即時視覺化。

## 📁 目錄結構
* `matlab_sim/`: TI-ADC 數學模型與數位校正演算法模擬。
* `rtl/`: 數位電路設計與硬體加速代碼。
* `firmware/`: 嵌入式系統 (C 語言) 驅動與通訊代碼。
* `software/`: Linux 數據處理系統。
* `hardware/`: LTspice 電路圖與 PCB 設計文檔。

## 🛠️ 開發環境
* **OS**: Windows 11 (Host) / Ubuntu 22.04 LTS (Remote-SSH)
* **Tools**: MATLAB, Vivado, LTspice, VS Code, GCC/G++