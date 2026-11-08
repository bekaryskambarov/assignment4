**Complexity:** Let L be total pattern length including duplicates, p dictionary size, and S trie states including the root. With the fixed 95-character ASCII alphabet, construction takes O(L+95*S+p) time and O(95*S+p) auxiliary memory. Reverse-failure propagation per independent text takes O(|text|+S+p). Output-link traversal instead takes O(|text|+z+p), where z counts visited terminal matches; it is not a guarantee of meeting the limits on dense inputs. Output memory is O(q*(p+1)+1) for q texts; retain one empty row per text when p=0. Avoid quadratically copied inherited output lists.

Example input:

{"task": "aho", "patterns": ["he", "she", "he"], "texts": ["sheshe", "sheshe", ""]}

One accepted result:

{"counts": [[2, 2, 2], [2, 2, 2], [0, 0, 0]]}

he is a suffix of she and is counted too. The repeated text starts with fresh counts.

**Explain:** Failure links, suffix-pattern counts, duplicates and independent texts.