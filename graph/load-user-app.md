flowchart TD
    A[开始] --> B{args是否为空?}
    B -- 是 --> C[返回InvalidInput错误]
    B -- 否 --> D[读取文件数据]
    D --> E[解析ELF文件]
    E --> F{是否存在Interp段?}
    F -- 是 --> G[获取解释器路径]
    G --> H{是否是特定解释器?}
    H -- 是 --> I[替换为/musl/lib/libc.so]
    H -- 否 --> J[规范化解释器路径]
    J --> K[构建新参数列表]
    K --> L[递归调用load_user_app]
    F -- 否 --> M[映射ELF文件]
    M --> N[初始化用户栈]
    N --> O[映射用户栈内存]
    O --> P[映射用户堆内存]
    P --> Q[计算用户栈指针]
    Q --> R[写入栈数据]
    R --> S[返回entry和user_sp]
    L --> T[返回递归结果]

   