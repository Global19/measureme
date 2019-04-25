# summarize

Summarize is a tool to produce a human readable summary of `measureme` profiling data.

## Example

```bash
$ git clone https://github.com/rust-lang/regex.git

$ cd regex

$ cargo rustc -- -Z self-profile

$ summarize pid-{pid}

+------------------------+-----------+-----------------+------------+------------+--------------+-----------------------+
| Item                   | Self time | % of total time | Item count | Cache hits | Blocked time | Incremental load time |
+------------------------+-----------+-----------------+------------+------------+--------------+-----------------------+
| LLVM_emit_obj          | 4.51s     | 41.432          | 141        | 0          | 0.00ns       | 0.00ns                |
+------------------------+-----------+-----------------+------------+------------+--------------+-----------------------+
| LLVM_module_passes     | 1.05s     | 9.626           | 140        | 0          | 0.00ns       | 0.00ns                |
+------------------------+-----------+-----------------+------------+------------+--------------+-----------------------+
| LLVM_make_bitcode      | 712.94ms  | 6.543           | 140        | 0          | 0.00ns       | 0.00ns                |
+------------------------+-----------+-----------------+------------+------------+--------------+-----------------------+
| typeck_tables_of       | 542.23ms  | 4.976           | 17470      | 16520      | 0.00ns       | 0.00ns                |
+------------------------+-----------+-----------------+------------+------------+--------------+-----------------------+
| codegen                | 366.82ms  | 3.366           | 141        | 0          | 0.00ns       | 0.00ns                |
+------------------------+-----------+-----------------+------------+------------+--------------+-----------------------+
| optimized_mir          | 188.22ms  | 1.727           | 11668      | 9114       | 0.00ns       | 0.00ns                |
+------------------------+-----------+-----------------+------------+------------+--------------+-----------------------+
| mir_built              | 156.30ms  | 1.434           | 2040       | 1020       | 0.00ns       | 0.00ns                |
+------------------------+-----------+-----------------+------------+------------+--------------+-----------------------+
| evaluate_obligation    | 151.95ms  | 1.394           | 33134      | 23817      | 0.00ns       | 0.00ns                |
+------------------------+-----------+-----------------+------------+------------+--------------+-----------------------+
| LLVM_compress_bitcode  | 126.55ms  | 1.161           | 140        | 0          | 0.00ns       | 0.00ns                |
+------------------------+-----------+-----------------+------------+------------+--------------+-----------------------+
| codegen crate          | 119.08ms  | 1.093           | 1          | 0          | 0.00ns       | 0.00ns                |
+------------------------+-----------+-----------------+------------+------------+--------------+-----------------------+
| mir_const              | 117.82ms  | 1.081           | 1050       | 30         | 0.00ns       | 0.00ns                |
+------------------------+-----------+-----------------+------------+------------+--------------+-----------------------+

(many more rows elided)

Total cpu time: 10.896488447s

```