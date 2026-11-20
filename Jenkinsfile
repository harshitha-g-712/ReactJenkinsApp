pipeline {
agent any
triggers {
pollSCM(&#39;H/2 * * * *&#39;)
}
tools {
nodejs &#39;NodeJS22&#39;
}
stages {
stage(&#39;Checkout Code&#39;) {
steps {
checkout scm
}
}
stage(&#39;Install Dependencies&#39;) {
steps {
bat &#39;npm ci&#39;
}
}
stage(&#39;Run Tests&#39;) {
steps {
bat &#39;npm test&#39;
}
}
stage(&#39;Build React&#39;) {
steps {
bat &#39;npm run build&#39;
}
}
stage(&#39;Archive Artifacts&#39;) {
steps {
archiveArtifacts artifacts: &#39;dist/**/*&#39;,
fingerprint: true
}
}
}
}