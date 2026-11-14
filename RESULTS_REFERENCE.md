# Results: 306 FIO NVMe Sweep

**Main goal:** Measure fio IOPS, bandwidth, and latency across a yaml sweep  
**Tools:** Run the system fio executable with --output-format=json and libaio against yaml filename

Reference results measured by the maintainer on the system shown in each section (generator TEMPLATE_00_140 · recorded 2026-11-13). Your own runs write `results/RESULTS_ACTUAL.md` in the same format.

> Smoke runs use deliberately small sizes. They check that the workload installs and runs end to end; their numbers are not performance results. Baseline and extended are.

<!-- profile:smoke -->
## smoke

- **System:** 1× AMD Instinct MI300X VF (196288 MB) · INTEL(R) XEON(R) PLATINUM 8568Y+ · Ubuntu 26.04.1 LTS · kernel 7.0.0-38-generic · driver 7.1.9.31600000
- **Run:** 2026-11-13T20:23:46Z · status **PASS** (exit 0)
- **Time (mm:ss):** setup 00:13 · benchmark 00:11 · whole run 00:31
- **Source:** run 306_20261113_202346
- **Command:** `bash run_benchmark.sh --smoke --io-engine libaio --filename data/fio_target.bin --direct 1 --rw randread --block-size 4k --size 64m --io-depth 1,8 --num-jobs 4 --warmup-duration-sec 0 --runtime 5`

| # | Metric | Result |
|---|---|---|
| 1 | IOPS mean at first sweep case (iops_mean) | 53535.892821 |
| 2 | Bandwidth at first sweep case, MB/s (bandwidth_mb_s) | 219.283016 |
| 3 | Completion latency p50 at first sweep case, us (clat_p50_us) | 80.384 |
| 4 | IOPS, 4k random read, iodepth 8 x 4 jobs = 32 in flight, every profile (iops_mean__randread_4k_qd8) | 174937.212557 |
<!-- /profile:smoke -->
