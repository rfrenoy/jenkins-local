# pipeline-developer

This is a jenkins server for developing pipelines locally without requiring git commits.

Login/Pass for Jenkins : `admin:admin` 

## Usage

#### To use included jenkins container
1. Map your volume in docker-compose
2. Run `docker-compose up`
3. Configure your multi-pipeline job by referring to the path mapped in step 1
4. There is docker registry accessible at `http://localhost:5000/`
