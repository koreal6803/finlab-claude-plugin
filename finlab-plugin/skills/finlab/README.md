# FinLab Skill TODO

## Pending Improvements

### High Priority (Completed)
- [x] Add MACD/KD/RSI golden cross examples
- [x] Add three institutional investors combo example

### Medium Priority
- [ ] Add inventory helper function to simplify shareholding analysis
- [ ] Add data update frequency table to data-reference.md
- [ ] Add Quick Reference Card (quick-reference.md)

### Low Priority
- [ ] Add FAQ document
- [ ] Add environment setup guide in SKILL.md
- [ ] Add continuous dividend detection example

---

## Suggested Additions

### Inventory Helper (for dataframe-reference.md)
```python
def get_inventory_by_level(inventory, min_level=12, max_level=15):
    """Get shareholding ratio by level (1-8: retail, 12-15: major holders)"""
    from finlab.dataframe import FinlabDataFrame
    result = inventory[
        (inventory.持股分級.astype(int) >= min_level) &
        (inventory.持股分級.astype(int) <= max_level)
    ].reset_index().groupby(["date", "stock_id"]).agg({
        "占集保庫存數比例": "sum"
    }).reset_index().pivot("date", "stock_id")["占集保庫存數比例"]
    return FinlabDataFrame(result)
```

### Data Update Frequency (for data-reference.md)
| Data Type | Frequency | Delay |
|-----------|-----------|-------|
| price | Daily | T+0 |
| institutional_investors | Daily | T+0 |
| inventory | Weekly | Friday |
| monthly_revenue | Monthly | Before 10th |
| fundamental_features | Quarterly | After report |

### Environment Setup (for SKILL.md header)
```
## Requirements
- Python >= 3.8
- pip install finlab
- If numpy issues: pip install 'numpy<2' pandas
```
