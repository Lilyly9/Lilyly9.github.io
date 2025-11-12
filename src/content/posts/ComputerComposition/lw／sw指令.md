# lw／sw指令

1. <span data-type="text" style="color: var(--b3-font-color9);">lw</span>  \$ t0 , 100(\$ t1)

    - ​`$t0`​  ←  以 `$t1`​为基地址，加上100得到的 **有效内存地址** ，把有效内存地址中的数据写入

    - 将内存中地址为 `$t1 + Imm`​ 的数据读取出来，写入寄存器 `$t0` 中

    ---
2. <span data-type="text" style="color: var(--b3-font-color9);">sw</span>  \$ t0 , 100(\$ t1)

    - ​`$t0`​   →   `$t1`​ 为基地址，加上100得到 **有效内存地址** ，被写入 `t0` 中的数据

    - 将寄存器`$t0`​中的数据，写入内存中地址为`$t1 + Imm`的位置

‍
