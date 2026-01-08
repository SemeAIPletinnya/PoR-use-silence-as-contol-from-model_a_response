# Experiment 002: Drift Accumulation

## Hypothesis

Drift accumulates over conversation turns, eventually triggering silence.

## Setup

- Model: GPT-4
- Conversation length: 50 turns
- Metric: Drift measured every 5 turns

## Protocol

1. Start conversation
2. Continue for 50 turns
3. Measure drift at turns 5, 10, 15, ..., 50
4. Plot drift over time

## Expected Result

Drift should increase monotonically, crossing 0.3 threshold at some point.

## Results

[To be filled after experiment]
