# criticalsignals.nz

## Dev

NOTE: we want to display pages with future dates so

```bash
git submodule update --init --recursive --depth 1
hugo serve --buildFuture
```

For CLI tool which offers interactive configuration:
```bash
npx blowfish-tools
```

## Color Scheme

```bash
cd ..
git clone https://github.com/nunocoracao/fugu.git
cd fugu
npm i
```

Inputs are <neutral> <primary> <secondary>
```bash
./index.js generate F8F4CE 194021 FF00FF > ../criticalsignals.nz/assets/css/schemes/crit-sigs.css 
# NOTE: you may have to go in and comment out the first line
```

Hmm... this didn't really work so ended up manually inspecting which css
was being used then putting the associated codes in:

Green: 194021 => rgb(25, 64, 33)
Cream: F8F4CE => rgb(248, 244, 206)


## Deploy

```bash
sudo wg-quick up nikau91
ssh sitedev@10.89.22.91
./update.sh
```
Install site, then when down 

```bash
sudo wg-quick down nikau91
```

