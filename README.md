# Bluver-view
router.get('/posts', async (req, res) => {
    const posts = await Post.find().sort({ createdAt: -1 }).populate('userId', 'username profilePicture');
    res.json(posts);
});

router.get('/profile/:userId', async (req, res) => {
    const user = await User.findById(req.params.userId);
    const posts = await Post.find({ userId: req.params.userId });
    res.json({ user, posts });
});
