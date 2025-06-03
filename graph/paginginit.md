sequenceDiagram
    axruntime->>axmm: init_memory_management
axmm->>axmm: new_kernel_aspace
axmm->>axhal: memory_regions
axhal-->>axmm: Returns list of memory regions
loop for each memory region
axmm->>axmm: aspace.map_linear
end
axmm->>axmm: KERNEL_ASPACE.init_once
axmm->>axhal: set_kernel_page_table_root
axruntime->>axalloc:1
axalloc->>axalloc: Initialize page allocator
axalloc->>axalloc:Initialize byte allocator