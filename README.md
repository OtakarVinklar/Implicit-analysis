## Manual for trying out the import

```bash
git clone https://github.com/OtakarVinklar/Implicit-analysis-wrapper
cd Implicits-analysis-wrapper
# Downloading scala-implicits-analysis project
# inside the Implicit-analysis-wrapper project
git clone --single-branch --branch new-neo4j-cache https://github.com/PRL-PRG/scala-implicits-analysis

# building docker image prlprg/implicit-analysis-pipeline
make -C docker

# Building scala libraries
./run.sh make -C scala-implicits-analysis/libs

# Validating the implicits.bin file
./run.sh amm scala-implicits-analysis/scripts/implicits-validate-for-graphcreation.sc example
# Running the import
# the graph database files are created in the example folder
./run.sh amm scala-implicits-analysis/scripts/create-graph-db.sc example

# Running Neo4j server
./runNeo4jDocker example
```
