stage('Build'){
    packpack = new org.tarantool.packpack()

    matrix = packpack.filterMatrix(
        packpack.default_matrix,
        {!(it['OS'] == 'el' && it['DIST'] == '6') &&
         !(it['OS'] == 'ubuntu' && it['DIST'] == 'precise')})

    node {
        checkout scm
        packpack.prepareSources()
    }
    packpack.packpackBuildMatrix('result', matrix)
}
