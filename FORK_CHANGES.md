# Fork Changes

This file records behavior changes made in this fork relative to upstream OrcaSlicer.

## Model Start Point

- Added `model_start_point_enabled`, `model_start_point_x`, and `model_start_point_y`.
- When enabled, Orca starts each configured object's first actual model perimeter near that object's configured absolute bed coordinate.
- The options may be supplied on object metadata or on part metadata in `Metadata/model_settings.config`; part metadata is promoted to the owning object for this feature.
- Skirts, brims, supports, and infill are not affected.
- The override is consumed once per object.
- The override applies to both normal and spiral/vase mode, including bottom/base layers.

## Middleware Runtime Image

- Added a GitHub Actions workflow to build this fork into a shared Docker runtime image for the slicer middleware.
- Added `Dockerfile.orca-runtime`, which packages `build/package` into `/opt/orcaslicer` and exposes `/opt/orcaslicer/AppRun`.
