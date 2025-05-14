graph TD;
    A[访问用户地址空间] --> B[UserPtr/UserConstPtr 包装器]
B-->C[验证指针]
C-->D[对齐]
C-->E[权限]
C-->F[完成映射]
D-->G{有效?}
E-->G
F-->G
G -- 是 --> H[安全访问]
H --> I[处理数据]
G -- 否 --> J[返回 EFAULT 错误]
J --> K[返回结果]
I -->K
