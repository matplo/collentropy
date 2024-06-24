# setup on hiccup

-- first (once) do this:

```
workdir=/software/users/$USER/mycollentropy
mkdir -p $workdir
cd $workdir
python3 -m virtualenv collentropyenv
source collentropyenv/bin/activate
python -m pip install --upgrade pip
python -m pip install numpy tqdm pyyaml

# load some preinstalled packages
module use /software/users/ploskon/yasp/software/modules
module load bundle/hepbase
module load heppyy/current
```

-- at the next login/shell (no need to create the python env)

```
workdir=/software/users/$USER/mycollentropy
source $workdir/collentropyenv/bin/activate
module use /software/users/ploskon/yasp/software/modules
module load bundle/hepbase
module load heppyy/current
```

- note: starlight command should be available now (and compiled with dpmjet...)

# generate some pythia events:

## get the code

```
workdir=/software/users/$USER/mycollentropy
cd $workdir
git clone git@github.com:matplo/collentropy.git
```

## generate

## this is for some inelastic events
```
./collentropy/gen/pythia_parts2root.py --nev 1000 --py-ecm 7000. --py-inel --output pythia_7TeV_inel.root
```

## this is for some non-single diffractive events

```
./collentropy/gen/pythia_parts2root.py --nev 1000 --py-ecm 7000. --py-nsd --output pythia_7TeV_nsd.root
```
