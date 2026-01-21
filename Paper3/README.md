# results_sorted

Este diretório contém resultados organizados de experimentos (BRKGA, MIP e comparações de decodificadores), além de listas de instâncias. Abaixo está um resumo da estrutura e do conteúdo dos arquivos.

## Estrutura de pastas

- `results_sorted/`
  - `brkga_results_by_instance_00.csv`
  - `brkga_results_by_instance_01.csv`
  - `brkga_results_by_instance_02.csv`
  - `brkga_results_big_instances.csv`
  - `brkga_results_small_instances.csv`
  - `brkga_mip_small_results_00.csv`
  - `brkga_mip_small_results_01.csv`
  - `brkga_mip_small_results_02.csv`
  - `decoder_comparision_grouped_00.csv`
  - `decoder_comparision_grouped_01.csv`
  - `decoder_comparision_grouped_02.csv`
  - `decoder_big_comparision_grouped_00.csv`
  - `decoder_big_comparision_grouped_01.csv`
  - `decoder_big_comparision_grouped_02.csv`
  - `mip_results_small.csv`
  - `mip_results_bigs.csv`
  - `mip_results_relax.csv`
  - `instances.csv`
  - `small_instances.csv`
  - `instances.json`
  - `guillherme/`
  - `lower_bounds/`
  - `mips/`

## Arquivos (nível raiz)

- `results_sorted/instances.csv` — lista de instâncias com colunas `instance_file,instance,jobs,stages`.
- `results_sorted/small_instances.csv` — lista de instâncias pequenas; colunas ` _file,instance,jobs,stages` (o cabeçalho começa com `_file`).
- `results_sorted/instances.json` — agrupamento de instâncias por combinação `jobs_stages` (ex.: `"50_05"`), com pares `id -> arquivo`.

- `results_sorted/brkga_results_by_instance_00.csv` — resultados do BRKGA por instância. Cabeçalho inclui métricas para `d0` e `d1` (médias, mínimos, CV e tempo de última melhoria). O cabeçalho tem nomes repetidos (ex.: `solution_d0` aparece várias vezes) exatamente como exportado.
- `results_sorted/brkga_results_by_instance_01.csv` — mesma estrutura do arquivo `_00` para outro conjunto/rodada.
- `results_sorted/brkga_results_by_instance_02.csv` — mesma estrutura do arquivo `_00` para outro conjunto/rodada.

- `results_sorted/brkga_results_big_instances.csv` — resultados brutos do BRKGA para instâncias grandes. Colunas incluem `experiment,instance,alpha,decoder,solution,time,last_improvment_time,generations,last_improvment_iteration,restarts,grater_inprovment_distnace,sum,nun`.
- `results_sorted/brkga_results_small_instances.csv` — resultados brutos do BRKGA para instâncias pequenas com o mesmo conjunto de colunas do arquivo de instâncias grandes.

- `results_sorted/brkga_mip_small_results_00.csv` — agregação MIP/BRKGA para instâncias pequenas, por número de jobs. Colunas incluem `jobs,instance_count,time,instance_sol_d0,instance_min_0,gap_0_mean,time_d0,instance_sol_d1,instance_min_1,gap_1_mean,time_d1`.
- `results_sorted/brkga_mip_small_results_01.csv` — mesma estrutura do arquivo `_00` para outro conjunto/rodada.
- `results_sorted/brkga_mip_small_results_02.csv` — mesma estrutura do arquivo `_00` para outro conjunto/rodada.

- `results_sorted/decoder_comparision_grouped_00.csv` — comparação agrupada entre decodificadores (`d0` e `d1`) por `jobs,stages,alpha`. Cabeçalho com colunas repetidas (ex.: `solution_d0`/`solution_d1` para média, mínimo e CV).
- `results_sorted/decoder_comparision_grouped_01.csv` — mesma estrutura do arquivo `_00` para outro conjunto/rodada.
- `results_sorted/decoder_comparision_grouped_02.csv` — mesma estrutura do arquivo `_00` para outro conjunto/rodada.

- `results_sorted/decoder_big_comparision_grouped_00.csv` — mesma estrutura da comparação agrupada, para instâncias grandes.
- `results_sorted/decoder_big_comparision_grouped_01.csv` — mesma estrutura do arquivo `_00` para outro conjunto/rodada.
- `results_sorted/decoder_big_comparision_grouped_02.csv` — mesma estrutura do arquivo `_00` para outro conjunto/rodada.

- `results_sorted/mip_results_small.csv` — resultados MIP para instâncias pequenas. Colunas: `instance,alpha,solution,time,gap,lb,nodes,ub`.
- `results_sorted/mip_results_bigs.csv` — resultados MIP para instâncias grandes (mesmas colunas do arquivo de instâncias pequenas).
- `results_sorted/mip_results_relax.csv` — resultados MIP relaxado (mesmas colunas; valores `inf` e `-inf` aparecem nas colunas de limites).

## Subpastas

### `results_sorted/guillherme/` resultado de aplicar o BRKGA BN-RT3 com o aplicativo do Guillherme.
Arquivos de resultados no formato `ID;FO;tempo;` (separador `;`). Cada arquivo corresponde a um conjunto/tamanho diferente:

- `results_sorted/guillherme/Result.txt`
- `results_sorted/guillherme/Result2.txt`
- `results_sorted/guillherme/Result3.txt`
- `results_sorted/guillherme/Result4.txt`
- `results_sorted/guillherme/Result1000.txt`
- `results_sorted/guillherme/Result1100.txt`
- `results_sorted/guillherme/Result2000.txt`
- `results_sorted/guillherme/Result6000.txt`
- `results_sorted/guillherme/Result10000.txt`
- `results_sorted/guillherme/Result15000.txt`
- `results_sorted/guillherme/Result25000.txt`

### `results_sorted/mips/`
Resultados MIP em arquivos `.txt` sem cabeçalho, separados por tab. As colunas seguem o padrão: `instance, alpha, solution, time, gap, lb, nodes, ub`.

- `results_sorted/mips/small/` — resultados para instâncias pequenas, um arquivo por conjunto (ex.: `0AllResult.txt`, `1031AllResult.txt`, ...).
- `results_sorted/mips/relax/` — resultados do MIP relaxado (ex.: `0RelaxAllResult.txt`, `100RelaxAllResult.txt`, ...). Inclui `inf`/`-inf` nas colunas de limites.
- `results_sorted/mips/bigs/` — resultados para instâncias grandes. Arquivos nomeados por `alpha` (ex.: `alpha_0AllResult.txt`, `alpha__55AllResult.txt`, ...).

### `results_sorted/lower_bounds/`
Resultados de lower bounds. Arquivos CSV com resultados do projeto do Guilherme e comparativos.

- `results_sorted/lower_bounds/Small_LBTT0.csv` — resultados do projeto do Guilherme (LBTT0).
- `results_sorted/lower_bounds/LBTT0_LBTT.csv` — resultados combinados de LBTT0 e LBTT.
