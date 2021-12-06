- metadata needs title

process:
# workflow test

- vist Google Drive folder of transcripts, select download of whole folder. This results in a zipped folder of ".docx" files.
- unzip
- Use Pandoc to convert the folder of .docx files into Markdown ".md" files. 
- Use command line to add empty "yaml frontmatter" (required to use in Jekyll)
- add all the .md transcript files to a folder in the collectionbuilder project called "_transcripts" (this makes them a Jekyll "collection" that we can use as data when the site builds)
- Prep the metadata:
    - Downloaded Pilot-1-MBR-Gale sheet as a CSV
    - add an "objectid" column
    - add iso "date" column
    - clean the column names a bit
    - add a "transcript_filename" column. We need a way to connect the metadata to the transcript files. The transcripts seemed to be named using a convention like "1-MBR-Gale-Transcription" which matched the metadata fields "Entry #" then the specific sheet name "MBR-Gale", so I just used that to add the column.
    - added a "title" field. I wasn't sure what to put in here--I just put the "Rebellion" + "Entry #" column for the quick demo. It would be better to use the article title, which is listed at the top of the transcript text, but not in the metadata.

With that set up I added a custom item layout to use for the transcript items. The item pages are built from the the metadata. It uses the "transcript_filename" field to pull in the text from the correct transcript file to display. 

## Thoughts

Keys:

- Make sure the transcript filenames exactly MATCH something in the metadata following a convention, or simply add a "transcript_filename" field to the metadata (in addition to the google doc link). In the demo collection there seems to be some transcripts that do not actually match their metadata--so there is probably already some issues with how I generated the field, since the convention doesn't exactly match.
- Metadata should have a title field, probably makes sense to use the article title that is listed in the transcripts. 
- The transcript files currently contain a little metadata paragraph at the top. Since I am just automatically converting them, this is still in the text displayed. It might make sense to remove that (since all that information should be in the metadata Sheet), or mark it in some way so it could be automatically removed for the collection? It seems structured and consistent enough that I may be able to convert it into front matter or metadata.

