# Hotdog | Not Hotdog

This model is based on the premise from Silicon Valley Season 4 | Episode 4:
https://www.youtube.com/watch?v=ACmydtFDTGs 

## Dataset

1. The HuggingFace Food101 Dataset was used, split down to hotdog (750) and non-hotdog.

1. `non-hotdog` instances were reduced to a sampling of 750.

1. Data was re-combined and then split into a training and validation set.

1. The `google/vit-base-patch16-224-in21k` model checkpoint was built off, utilizing `transfer learning`

    > This can significantly reduce both the training time, as well as the need for large, labeled datasets, since the model has already learned a set of features that can be applicable to the new task.

1. Normalization and transforms are defined and applied to reduce overfitting (gotta be honest, I pulled this from the Interwebs)

1. A Data collator is defined in order to batch the data

1. Accuracy and metric functions (also yanked from Interwebs) to compute accuracy of the model

1. All labels are then mapped (even though we know it's just `0` and `1` for `hot_dog` and `not_hot_dog`)

1. Load the model from the pretrained Image classification transformer

1. Training arguments are defined (these are just defaults)

1. Train the model!