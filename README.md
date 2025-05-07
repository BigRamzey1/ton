The commit [`aa162aeaf75b15629137b11936fbb9d3df11a789`](https://github.com/ton-blockchain/ton/commit/aa162aeaf75b15629137b11936fbb9d3df11a789) in the TON Blockchain repository contains the following changes:

### Summary Details
- **Author**: [SpyCheese](https://github.com/SpyCheese)
- **Date**: 2025-05-05
- **Message**: Merge branch `archive-sync` into `accelerator`
- **Parent Commits**:
  - [`44705a1`](https://github.com/ton-blockchain/ton/commit/44705a1bcbb0b1e98ccf662e9ec6d6c778ebec3d)
  - [`57037a9`](https://github.com/ton-blockchain/ton/commit/57037a9f8cce0a397b501d149d9c0407e98f97b2)

### Change Statistics
- **Additions**: 1711 lines
- **Deletions**: 101 lines
- **Total Changes**: 1812 lines

### Files Modified
Here are the main file modifications:

1. **`crypto/block/mc-config.h`**
   - **Change**: Updated method `get_cur_validator_set` to return a `shared_ptr<ValidatorSet>`.
   - **Additions**: 2 lines, **Deletions**: 2 lines.

2. **`crypto/vm/db/CellStorage.cpp`**
   - **Change**: Enhanced `RefcntCellStorer` to support `max_level` for improved cell storage functionality.
   - **Additions**: 25 lines, **Deletions**: 8 lines.

3. **`crypto/vm/db/CellStorage.h`**
   - **Change**: Added `max_level` parameter in `serialize_value` method.
   - **Additions**: 2 lines, **Deletions**: 1 line.

4. **`utils/CMakeLists.txt`**
   - **Change**: Added a new executable `prepare-ls-slice-config`.
   - **Additions**: 3 lines.

5. **`utils/prepare-ls-slice-config.cpp`**
   - **Change**: New file added to generate `liteserver.descV2.Slice` configurations.
   - **Additions**: 266 lines.

6. **`validator-engine/validator-engine.cpp`**
   - **Change**: Added new options for `permanent_celldb` and `sync_shards_upto`.
   - **Additions**: 34 lines, **Deletions**: 9 lines.

7. **`validator-engine/validator-engine.hpp`**
   - **Change**: Added new fields and methods for `permanent_celldb` and `sync_shards_upto`.
   - **Additions**: 12 lines.

8. **`validator/CMakeLists.txt`**
   - **Change**: Included new files for permanent CellDB utilities.
   - **Additions**: 4 lines.

9. **`validator/db/celldb.cpp`**
   - **Change**: Significant updates for permanent CellDB functionality.
   - **Additions**: 203 lines, **Deletions**: 4 lines.

10. **`validator/db/celldb.hpp`**
    - **Change**: Added methods for storing blocks in permanent mode.
    - **Additions**: 8 lines.

---

### Notable Changes
- **CellDB Enhancements**:
  - Introduced permanent mode for CellDB, allowing blocks to be stored without garbage collection.
  - Added bulk operations for storing blocks in permanent mode.

- **New Utility**:
  - Added `prepare-ls-slice-config.cpp` for generating configurations.

- **Validator Engine Updates**:
  - Added support for skipping key synchronization and setting shard synchronization limits.

For a complete view, check out the [commit details here](https://github.com/ton-blockchain/ton/commit/aa162aeaf75b15629137b11936fbb9d3df11a789). Let me know if you need further analysis or explanation of specific changes!