# Kenel_Namespace

Namespace 命名空間可以讓 process group 擁有獨立 ID、IPC 與網路空間。

分割命名空間的方式：

    # clone system call
    // 第三個引數 flags 指定要分割出命名空間的旗標，接著分割命名空間。
    // 建立好新的 PID 後，從 1 開始編號。
    
不同 PID 可能編號相同，但是彼此毫無關係，而一 PID fork() 出來的 processs 會被關在這 Process 的命名空間之內，與其他 PID 隔離。

同樣地，IPC、網路、檔案系統掛載空間、UTS (Universal Time Sharing System) 也能當成分割對象。
