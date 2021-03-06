## Test example ##
Run `infCalc.py` without arguments for help
```bash
# displays useful (hopefully) help message
~/path/to/runInfCalc.sh
# DBG: __SRC_PATH: /home/aram/dev-src/infstats_calc
# DBG: sys.argv: ['/home/aram/dev-src/infstats_calc/infCalc.py']
# usage: /home/aram/dev-src/infstats_calc/infCalc.py [-h | -c ctl_file |
#            --vir_aln=align1 --host_aln=align2
#            --vir_keep=keep1 --host_keep=keep2
#            --seqID_pairs=virushost.pair ]
#          [-o | --outdir directory]
#          [-T num_threads]
```

#### control file ####
`test.ctl` is the test control file for this example run.

- Tab delimited
- Lines starting with `#` are ignored.
- Unused options are ignored
- Command line options override control file
- Full paths are recommended
  (eg. `/path/to/data/foo/bar/baz.phy` might be different from `foo/bar/baz.phy`)

#### (vir | host).phy ####
A Phyllip alignment file.

- First line is a space followed by `%d %d'`.
  - The first `%d` is the number of sequences
  - The second `%d` is the number of columns
- Lines 2 to last: One sequence per line.
  - First 10 characters are sequence identifier.
  - Characters 11 to EOL are sequence
- For compatibility, only the first 8 chars are used in sequence identifier (9, 10 are spaces).
- Whitespace is stripped from sequence

#### vir_host.out ####
Example output

- Tab delimited
- First line is header (uncommented)
- Column indices start at 0
- Entropies and their sums are in nats
- Zmin_MutInf and Zjoint_MutInf are unitless

#### seqID.pairs ####
Tells infCalc.py which sequences are paired

- Tab delimited
