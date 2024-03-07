### SD540-MongoDB-02
GIven the following Schema:
```typescript
const CommentSchema = new Schema({
    text: { type: String, required: true },
    user: {
        email: { type: String, required: true },
        name: { type: String, required: true }
    },
}, { timestamps: true });

const PostSchema = new Schema({
    title: { type: String, required: true },
    body: { type: String, required: true },
    draft: { type: Boolean, default: true },
    comments: [CommentSchema],
}, { timestamps: true });

type Post = InferSchemaType<typeof PostSchema>;
type Comment = InferSchemaType<typeof CommentSchema>;

const PostModel = model<Post>('post', PostSchema);
```
* Write a function to add a new post.
* Write a function to add a new comment. Add multiple comments by multiple users.
* Write a function to return all comments created by a user, with pagination.
* Write a function to add multiple comments.
* Write a function to update a comment text by user's email.
* Write a function to update the user name, in all comments created by a user.
* Write a function to delete all comments created by a user.
