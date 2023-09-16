Imports:
```
from tracker.bot_sort import BoTSORT
```

Run:
```
bot_sort = BoTSORT()

for image, boxes_with_scores in zip(images, detection_results):
    # boxes_with_scores: np.ndarray, shape - (n, 5) (or (n, 6) if with classes ids)
    #     [:, :4] - boxes xyxy
    #     [:, 4] - scores
    #     [:, 5] - classes ids (optional)
    # infos (optional): array of n elements
    tracked_objects = byte_track.update(boxes_with_scores, image, infos=infos)  # can accept masks
    # tracked_objects: list of STrack
    # STrack:
    #     track_id
    #     tlwh, tlbr, xywh (xy is center)
    #     class_id (default: -1)
    #     info (optional)
```
