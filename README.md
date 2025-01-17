# `prodigal-gv`

A fork of [Prodigal](https://github.com/hyattpd/Prodigal) meant to improve gene calling for giant viruses and viruses that use alternative genetic codes. It includes ten models added to the metagenome mode:
* *Acanthamoeba polyphaga mimivirus*
* *Paramecium bursaria* Chlorella virus
* *Acanthocystis turfacea* Chlorella virus
* [VirSorter2](https://github.com/jiarong/VirSorter2)'s NCLDV gene model
* [Topaz (genetic code 15)](https://www.biorxiv.org/content/10.1101/2021.08.26.457843v1.full)
* [Agate (genetic code 15)](https://www.biorxiv.org/content/10.1101/2021.08.26.457843v1.full)
* Gut phages (genetic code 15)
* Gut phages (genetic code 11) × 5

## Citation

If you use `prodigal-gv`, please cite:

> Camargo, A. P., Roux, S., Schulz, F., Babinski, M., Xu, Y., Hu, B., ... and Kyrpides, N. C. (2023). [Identification of mobile genetic elements with geNomad](https://www.nature.com/articles/s41587-023-01953-y). Nature Biotechnology, *1-10*.

Prodigal was written by [Doug Hyatt](https://github.com/hyattpd/) and its usage should be acknowledged.

> Hyatt, D., Chen, G.-L., LoCascio, P.F., Land, M.L., Larimer, F.W., and Hauser, L.J. (2010). [Prodigal: prokaryotic gene recognition and translation initiation site identification](https://bmcbioinformatics.biomedcentral.com/articles/10.1186/1471-2105-11-119). BMC Bioinformatics *11*, 119.

## Installation

`prodigal-gv` can be installed via [Conda/Mamba](https://anaconda.org/bioconda/prodigal-gv), pre-build binaries ([Linux](https://github.com/apcamargo/prodigal-gv/releases/download/2.10.0/prodigal-gv-linux) and [macOS](https://github.com/apcamargo/prodigal-gv/releases/download/2.10.0/prodigal-gv-macos)), or built from scratch:

```
# Conda/Mamba:
conda install -c bioconda prodigal-gv

# Pre-built binary (Linux):
curl -L https://github.com/apcamargo/prodigal-gv/releases/download/2.10.0/prodigal-gv-linux -o prodigal-gv
chmod +x prodigal-gv

# Pre-built binary (macOS):
curl -L https://github.com/apcamargo/prodigal-gv/releases/download/2.10.0/prodigal-gv-macos -o prodigal-gv
chmod +x prodigal-gv

# Buld from scratch
git clone https://github.com/apcamargo/prodigal-gv.git
cd prodigal-gv
make
```

## Usage

```bash
prodigal-gv -p meta -i genome.fna -a proteins.faa > /dev/null 2>&1
```

## Parallelized execution

[`parallel-prodigal-gv.py`](https://github.com/apcamargo/prodigal-gv/blob/master/parallel-prodigal-gv.py) is a script that allows parallelized execution of `prodigal-gv`:

```
./parallel-prodigal-gv.py -t 8 -q -i genome.fna -a proteins.faa
```
