@RestController
@RequiredArgsConstructor
public class UpdateCommentController {
    final UpdateComment updateComment;

    @PostMapping("/updateComment")
    void update(@RequestBody UpdateComment.Request request, @AuthenticationPrincipal SudirUser sudirUser) {
        updateComment.update(request, sudirUser.getUsername());
    }
}
