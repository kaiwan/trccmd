# trccmd
A trace-cmd frontend

======= trccmd Help screen =======

Usage:
trccmd [-h] [-e 'subsystem1 subsystem2 ...'] [-F 'program-to-trace [arg1] [arg2] ...']

 Eg. ./trccmd -e 'syscalls kmem' -F 'ps -LA'

 NOTE:
 a) -F: this will perform an _exclusive_ ftrace of the provided app ('ps -LA' in the above eg).
 b) -e: the -e 'events' switch allows you to trace particular subsystems (default: all)! Pick
    from among the ones shown below; you can specify as many as you like, just separate them
	with a space:

alarmtimer amd_cpu asoc avc block bpf_test_run bpf_trace bridge cfg80211 cgroup clk compaction cpuhp cros_ec dev devfreq devlink dma_fence drm error_report events event systems exceptions ext4 fib fib6 filelock filemap fs_dax gpio gvt hda hda_controller hda_intel huge_memory hwmon hyperv i2c i915 initcall intel_iommu intel_ish interconnect iocost iomap iommu io_uring irq irq_matrix irq_vectors iwlwifi iwlwifi_data iwlwifi_io iwlwifi_msg iwlwifi_ucode jbd2 kmem kvm kvmmmu libata mac80211 mac80211_msg mce mdio mei migrate mmap mmap_lock mmc module mptcp msr napi neigh net netlink nmi nvme oom options page_isolation pagemap page_pool percpu power printk pwm qdisc ras raw_syscalls rcu regmap regulator resctrl rpm rseq rtc sched scsi signal skb smbus sock spi swiotlb sync_trace syscalls task tcp thermal thermal_power_allocator timer tlb tls tracers ucsi udp v4l2 vb2 vmscan vsyscall wbt workqueue writeback x86_fpu xdp xen xhci-hcd 

    Not using the -e option has trccmd attempt to trace _all_ events

 c) ensure you surround the -e and/or -F arguments with single quotes '...'
 d) If no program is provided as an argument, we shall trace-cmd(1) whatever's running on the system
 e) The config file's here:
     /home/kaiwan/.local/trccmd.config

 If you want to *see all function parameters and their runtime values*
 (useful!), ensure the variable SHOW_PARAMETERS is set to 1 in the config file
 (check it out, useful stuff within). You will, however, lose the function graph indentation
 when parameters are enabled.

 f) pass only '-h' to trccmd to see this Help screen.

 TIP:
 See (and try!) the sample_usage script.

Please do report bugs / suggestions, thank you!
