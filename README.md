Micrium/
└── Software/
    ├── uCOS-II/               <- RTOS 核心 (scheduler, task mgmt, etc.)
    │   ├── OS_CORE.C          <- 核心功能（排程器、hook 函式）
    │   ├── OS_TASK.C          <- 任務管理（建立、刪除、切換）
    │   ├── OS_TIME.C          <- 時間與延遲管理
    │   ├── OS_CPU_C.C         <- 與 CPU 相關的 context switch 實作
    │   ├── INCLUDES.H         <- 所有必要 include 的標頭檔
    │   └── ...
    └── BSP/                   <- Board Support Package（硬體抽象層）

例如在 os_core.c 或 os_task.c 檔案中進行修改：
更改了原本的優先權排程機制，讓它支援簡單的 round-robin 排程。

追蹤每次 context switch 發生時是哪兩個任務之間轉換。

透過在 OSTaskSwHook() 中加上輸出，來觀察排程行為
