# Pre-commit audit

## Publication decision

This is a new repository with no inherited Git history. Only files directly needed to explain the frozen baseline09 configuration, its public-network input and its model-derived validation outputs are included.

## Files prepared for commit

- `.gitignore`
- `LICENSE`
- `README.md`
- `config/am_baseline09.sumocfg`
- `network/george_town_core_v3.net.xml`
- `additional/am_outputs.add.xml`
- `demand/README.md`
- `outputs/baseline09_sanity_summary.csv`
- `outputs/corridor_summary.csv`
- `outputs/hotspot_ranking.csv`
- `docs/assumptions_and_limitations.md`
- `docs/selected_corridors.md`
- `docs/ATTRIBUTION.md`
- `docs/PRE_COMMIT_AUDIT.md`

## Excluded material

- `am_baseline08.rou.xml`: route-demand input omitted because its source evidence includes course-provided or third-party material whose public redistribution permission is not confirmed.
- Calibration inputs, traffic source data and demand-generation scripts: excluded for the same reason and because they contain local paths.
- Raw SUMO outputs, FCD trajectories, logs and temporary files: excluded because they are unnecessary for the documented validation release and may contain local paths.
- MATLAB EV analysis and all unrelated CIV5803 task materials: excluded because they are downstream analysis or outside baseline09 scope.

## Sanitisation performed

- Removed the NetEdit metadata comment containing local absolute paths from the network file.
- Replaced configuration and additional-file output references with repository-relative paths.
- Removed the local-path build scripts rather than rewriting them, because their required calibration inputs are not redistributed.
- Rephrased one documentation reference to avoid identifying course personnel.

## Security and privacy scan

The candidate files were recursively scanned for personally identifying information, local paths and standard credential indicators. No sensitive matches were found.

## Copyright and attribution review

The network is documented as OpenStreetMap-derived and carries an OpenStreetMap attribution and ODbL notice. Course-provided and third-party source inputs are omitted where redistribution permission is not confirmed.

## Configuration and run check

All committed XML files parse successfully. Eclipse SUMO 1.27.1 successfully ran the cleaned, repository-relative configuration when supplied temporarily with the authorised original route file; exit code was 0, with the pre-existing warning that one actuated traffic-light logic has link indices without controlling detectors. The temporary demand copy and all generated test outputs were deleted before staging.

## Reproducibility status

The repository is sufficient to inspect the frozen configuration, public-network input and published validation outputs. It is not independently runnable without the original authorised route-demand file, which must be placed at `demand/am_baseline08.rou.xml`.
