![alt text](https://www-cdn.qwertee.io/media/uploads/blog/deep_learning_with_point_clouds/conv.png)
![alt_text](data:image/png;base64,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)