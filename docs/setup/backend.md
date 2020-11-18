# Backend

This contains the code that downloads and extracts the data from the various raw sources, performs calculations, and produces data products. It also contains the setup for the [Geoserver](http://geoserver.org/) that serves up the data products to the front-end.

## Development
---

### Requirements

To make it easier to develop locally, we decided to use docker and Make.
The only requirements are docker and docker-compose.
If they are not installed on your machine, you can follow these steps to get started:
https://docs.docker.com/compose/install/

### Environment

You will need to setup a `.env` file with the required information. You can use `.env.sample` as an example.

### Data Files

To avoid checking in large files to the repository, we removed generated data files, SQL data, and Boundary/"shapefiles" used to filter data by country. In order to create data products or start the Geoserver, you will likely need to download additional files. You can download archives containing these files from the following links. Copy these archive files into the main `prism/backend` directory, then extract them to get the relevant files:

```
cd prism/backend
# Download the archive that you would like.
curl -O https://wfp-prism.s3-us-west-1.amazonaws.com/prism_sql_20191010.tar.gz
tar -xzvf prism_sql_20191010.tar.gz
```

Here are links to some import files:

- **Indonesia Shape Files:** https://wfp-prism.s3-us-west-1.amazonaws.com/prism_shapefiles_20191010.tar.gz
  These shapefiles are necessary to create data products for Indonesia.
- **Sample SQL data:** https://wfp-prism.s3-us-west-1.amazonaws.com/prism_sql_20191010.tar.gz
  This contains SQL dumps from data products created for Indonesia.
- **Mock Geoserver data:** https://wfp-prism.s3-us-west-1.amazonaws.com/prism_geoserver_mock_data_20191010.tar.gz
  This contains sample data products to allow the Geoserver to serve a "mock" response, or example of each time of data product.

If you would like to make your own archive with large files (remember, we don't want to check large files into the repo) that would be useful to your team, you can easily create your own archive. The easiest way to do this is to construct a `find` query that matches the files that you would like to share, and then create an archive using `tar`. For example, if you wanted to create an archive of all the `.tif` files in `geoserver_data`:

```
find geoserver_data -name *.tif -exec tar -czvf my_archive.tar.gz {} \;
```

This produces `my_archive.tar.gz`. `find` supports a wide variety of selectors, including regex.

### Running Products
A task runner script attempts to make tasks easy to run. It automatically starts Docker containers
and then runs tasks inside the containers. This script requires docker to be installed and 
configured in the local environment, and requires Python 3.6 to be installed.

To run the different products locally you can use the two following scripts. The runner scripts have runtime help available with `--help`. For many of the products (spi, vhi, dslr, rainfall_anomaly etc.), you'll also want to specify a date with the -d YYYY-MM-DD option (it defaults to using the current date, but that's usually not what you want to do).

```
./run_prism_task.py PRODUCT_NAME -d 2019-06-01

./scripts/backfill_data.py PRODUCT_NAME 2019-01-01 2019-11-01
```

Note that this script is merely a wrapper around to `./prism_process.py` that orchestrates the
Docker calls and better default argument handling.

By default, this command runs a "full" PRISM task, which includes generating a YAML task
configuration file (by default in `./config/{country}_{task}.yml`) and then running the task as 
defined by that file. If you would like to separate these steps (e.g. just generate the config file 
or just run a task based on an existing config file), you can do this:

**Generate a config (don't run the task)**
```
$ ./run_prism_task.py -o="generate_config" spi
```

**Run the task (without generating/overwriting a config)**
```
$ ./run_prism_task.py -o="run" spi
```

#### Available Products
To get started, we recommend getting access to pre-computed data, at least for the long term averages which can take a very long time to compute.

Here is a list of the different products available. Note that the underlying data might not always be available in the country of interest.

**Long Term Averages**
- evi_longterm_average
- chirps_longterm_average
- lst_longterm_average


**Products**
- days_since_last_rain
- flood_forecast
- vci
- tci
- vhi
- rainfall_anomaly
- spi

### Locally

To get started, simply run `make backend` from the main folder.

## Tests & Linters

To ensure consistency in code quality and calculation outcomes, we implemented a testing framework (pytest) and linters (pep8 + flake8) for Python.

All the functions of the Prism backend should be tested. The "test coverage" expectation will be set at 90%.