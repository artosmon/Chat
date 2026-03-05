public interface UpdateComment {

    void update(Request request, String authorLogin);

    @Value
    @Builder
    class Request {
        String pledgeId;
        String commentText;
    }
}
