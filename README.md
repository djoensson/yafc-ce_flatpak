## Update and build

- Update the submodules
`git submodule update --remote --merge`

- Checkout the new YAFC-CE version by doing
`git checkout tags/VERSION` in the repo

- Update the metadata in the .xml and .yaml file to point to the new release

- To generate the nuget-sources.json file, run the following 
`python3 flatpak-dotnet-generator.py --dotnet 8 --freedesktop 25.08 nuget-sources.json yafc-ce/Yafc/Yafc.csproj` 

- To build the flatpak, run: 
`flatpak run org.flatpak.Builder build-dir --user --force-clean --install --repo=repo io.github.YafcCE.yafc-ce.yaml`
