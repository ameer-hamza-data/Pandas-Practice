# AI Agent Guidelines for Pandas Learning Project

## Project Overview
This is a **Pandas/NumPy learning workspace** focused on data analysis, manipulation, and exploration using Jupyter notebooks.

**Key Files**:
- `02.ipynb` – Main learning notebook for pandas operations
- `ipl-matches.csv` – IPL cricket matches dataset
- `movies.csv` – Movies dataset

## When Suggesting Code

### Pandas Patterns
When working with DataFrames, suggest:
- **Data loading**: Use `pd.read_csv()` for CSV files; consider `index_col`, `dtype`, and `parse_dates` parameters
- **Data inspection**: Recommend `.head()`, `.info()`, `.describe()`, `.shape` for understanding data
- **Selection**: Prefer `.loc[]` and `.iloc[]` over direct bracket notation for clarity
- **Cleaning**: Suggest `.dropna()`, `.duplicated()`, `.astype()` with specific parameters
- **Aggregation**: Guide through `.groupby()`, `.agg()`, `.pivot_table()` for analysis
- **Merging**: Recommend `.merge()` over `.join()` with clear `on` parameters

### NumPy Patterns
When suggesting NumPy code:
- Explain vectorized operations over loops
- Use `.reshape()`, `.transpose()`, slicing for efficient manipulation
- Leverage NumPy's broadcasting capability
- Consider performance implications for large arrays

### Jupyter-Specific
- Suggest cell organization (imports first, then data loading, then analysis)
- Use `%%time` magic for performance checks if relevant
- Recommend `.to_csv()` with `index=False` to avoid unnecessary index columns

## Data Exploration Workflow

When helping with analysis, follow this sequence:
1. **Load & Inspect**: Read CSV → view shape, dtypes, null counts
2. **Understand**: Check unique values, distributions, correlations
3. **Clean**: Handle missing values, duplicates, type conversions
4. **Transform**: Create derived features, rename columns, filter rows
5. **Analyze**: Group, aggregate, pivot, sort by relevant dimensions

## Code Completion Hints

The workspace has VS Code settings that enable quick suggestions for:
- Pandas method completions (e.g., `.groupby`, `.merge`, `.apply`)
- NumPy functions (e.g., `np.array`, `np.mean`, `np.where`)
- DataFrame columns (via Pylance's type inference)

Leverage these when suggesting code that chains operations.

## Common Pitfalls to Avoid

- **Modifying in-place**: Clarify `.inplace=True` usage; prefer assignment for clarity
- **SettingWithCopyWarning**: Suggest `.copy()` when reassigning subsets
- **Chained indexing**: Use `.loc[]`/`.iloc[]` consistently
- **NaN handling**: Be explicit about whether to drop or fill NaNs

## File Descriptions

**ipl-matches.csv**: IPL cricket match data
- Likely contains: match_id, date, team1, team2, venue, winner, result_margin
- Use for: filtering by team, date ranges, aggregating wins/losses

**movies.csv**: Movie dataset
- Likely contains: title, genre, year, rating, revenue, runtime
- Use for: genre analysis, rating distributions, revenue trends

## For Notebook Improvements

When suggesting notebook enhancements:
- Add markdown cells explaining the analysis goal
- Suggest intermediate print/display statements for validation
- Recommend saving results to CSV for reuse
- Encourage comments on non-obvious operations
