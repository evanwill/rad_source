- metadata needs title

process:

- download transcripts as batch folder from google drive
- convert with pandoc to .md
- add front matter to files
- add md to collection _transcripts
- metadata:
    - add objectid
    - add iso date
    - clean column names
    - add transcript_filename 
- call in transcript on item page using transcript_filename field
