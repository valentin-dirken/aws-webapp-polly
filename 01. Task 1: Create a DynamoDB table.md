### Task 1: Create a DynamoDB Table

The application stores information about blog posts, including the text and URL of the MP3 file, in Amazon DynamoDB. You start by creating a `posts` table. The primary key (`id`) is a string, which the New Post Lambda function creates when new records (posts) are inserted into the database.

1. At the top of the AWS Management Console, in the search bar, search for and choose **DynamoDB**.
2. Choose **Create table**.
3. Create a new DynamoDB table with:
   - **Table name**: `posts`
   - **Partition key**: `id` (String)
   - **Table settings**: Default settings
4. Choose **Create table**.

There is no need to define the whole structure of the table now. After you complete the application setup, it stores the following information in the DynamoDB table:

- `id`: The ID of the post.
- `status`: UPDATED or PROCESSING, depending on whether an MP3 file has already been created.
- `text`: The post's text, for which an audio file is being created.
- `voice`: The Amazon Polly voice that was used to create the audio file.
- `url`: A link to an S3 bucket where an audio file is being stored.

**Task Complete**

You can now proceed to the next task.
