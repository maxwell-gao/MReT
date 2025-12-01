# Dataset Preparation
Adopted from [TinyRecursiveModels/README.md:](https://github.com/SamsungSAILMontreal/TinyRecursiveModels)

```bash
# ARC-AGI-1
uv run python -m data.build_arc_dataset \
  --input-file-prefix kaggle/combined/arc-agi \
  --output-dir data/sets/arc1concept-aug-1000 \
  --subsets training evaluation concept \
  --test-set-name evaluation

# ARC-AGI-2
uv run python -m data.build_arc_dataset \
  --input-file-prefix kaggle/combined/arc-agi \
  --output-dir data/sets/arc2concept-aug-1000 \
  --subsets training2 evaluation2 concept \
  --test-set-name evaluation2

## Note: You cannot train on both ARC-AGI-1 and ARC-AGI-2 and evaluate them both because ARC-AGI-2 training data contains some ARC-AGI-1 eval data

# Sudoku-Extreme
uv run python -m data.build_sudoku_dataset --output-dir data/sets/sudoku-extreme-1k-aug-1000  --subsample-size 1000 --num-aug 1000  # 1000 examples, 1000 augments

# Maze-Hard
uv run python -m data.build_maze_dataset # 1000 examples, 8 augments
```