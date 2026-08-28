#### rust_lang_rules
(Production-Rust rules of thumb)

# 🦀 Rust Guidelines 🦀:
- Always best practice
- Never ~unsafe code
- Always extensive doc strings: what the code is doing with project-context
- Always clear comments
- Include cargo tests (where possible)
- Functions should return result (in real life everything will fail at some point)
- Never remove (still-current) documentation
- Always clear, meaningful, unique names (e.g. variables, functions)
- Always absolute file paths
- Always error handling
- '?' should be avoided where it would obscure an error
- Never use unwrap (in production-release builds; use in cargo-tests is obviously valid)
- Always handle modes (test, debug, production-release) and cases/errors appropriately for that project
- Always follow boy-scout values

# 🦀 10 Rust Rules 🦀:
1. Avoid Risky Methodologies: 
- no recursion  
- no goto 
- no fancy pointer use 
- no preprocessor branching
('unsafe' code blocks in Rust may be unavoidable)

2. Loops: either firmly bounded or unbounded w/ recovery

3. Attempt to Pre-allocate all memory (stack, not heap)
- case by case, avoid heap in production-release-mode where sound

4. Clear Function Scope and Data Ownership

5. Mode & Case Handling, & Defensive-Programming: 
- Modes: test-mode, debug-mode, production-release-mode; 
- continual state-recovery (without panic/halt) in production-release-mode
- See example/default framework: https://github.com/lineality/modes_and_case_handling 

6. Manage ownership and borrowing

7. Manage return values

8. Manage conditional compilation

9. Communicate: 
- Use doc strings; use comments. 
- Document use-cases, edge-cases, policies, intent: features vs. bugs, etc.
- Rather than let _ =, allow that result to be shown in debugging
- log errors (MVP: append log file in executable-parent dir)

10. Use state-less operations when possible

#### Links:
- https://en.wikipedia.org/wiki/The_Power_of_10:_Rules_for_Developing_Safety-Critical_Code
- https://spinroot.com/gerard/pdf/P10.pdf 
- https://spinroot.com/static/index.html 
- https://web.eecs.umich.edu/~imarkov/10rules.pdf 
- https://en.wikipedia.org/wiki/Static_program_analysis 
- https://www.oreilly.com/library/view/designing-data-intensive-applications/9781491903063/
- https://www.oreilly.com/library/view/rust-atomics-and/9781098119430/ 

