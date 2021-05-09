# Installation 🖥️

## Install from source

{% hint style="info" %}
 To build from source, your PostgreSQL needs to include the development headers and utilities. 
{% endhint %}

With git, cmake and build essential tools, one can build and install postgeoda extension from source: 

```bash
git clone --recursive https://github.com/geodacenter/postgeoda
cd postgeoda
mkdir build
cd build

cmake -DCMAKE_BUILD_TYPE=Release ..
make
make install
```

## Dependencies

PostGeoDa has no dependencies. You don't need to install PostGIS.

## Enabling PostGeoDa

After installation, you need to enable PostGeoDa in each database that you want to use. Run the following SQL when you connect to your database:

```sql
CREATE EXTENSION postgeoda;
```

