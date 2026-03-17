local('docker build -t jekyll-dev -f Dockerfile.dev .', quiet=True)

local_resource(
    'jekyll-serve',
    serve_cmd=' '.join([
        'docker run --rm',
        '-v "%s:/site"' % os.getcwd(),
        '-p 4000:4000',
        '-p 35729:35729',
        'jekyll-dev',
    ]),
    deps=[
        '_layouts',
        '_includes',
        '_data',
        'assets',
        '_config.yml',
        'index.md',
        'research.md',
        'projects.md',
        'publications.md',
        'scientific-software.md',
        'team.md',
        'people.md',
    ],
    links=['http://localhost:4000'],
)
