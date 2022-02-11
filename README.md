# Sounds
An ontology for the description and classification of sounds.

### Generate the documentation website

Check the `.github/workflows/SounOntologyDoc.yml` file to see the steps to install the dependencies and run the commands to generate the ontology documentation.

Once you have generated the documentation locally in the `docs` folder you can start it on http://localhost:8080 with docker:

```bash
docker run -it --rm -p 8080:80 -v $(pwd)/docs:/usr/local/apache2/htdocs/ httpd:2.4
```
