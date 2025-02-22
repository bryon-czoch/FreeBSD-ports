PORTNAME=	cirrus-cli
PORTVERSION=	0.78.0
DISTVERSIONPREFIX=	v
CATEGORIES=	devel

MAINTAINER=	bofh@FreeBSD.org
COMMENT=	Command line interface for Cirrus CI

LICENSE=	AGPLv3
LICENSE_FILE=	${WRKSRC}/LICENSE

USES=		go:modules
USE_GITHUB=	yes
GH_ACCOUNT=	cirruslabs
GH_TUPLE=	\
		Microsoft:go-winio:v0.5.1:microsoft_go_winio/vendor/github.com/Microsoft/go-winio \
		PaesslerAG:gval:v1.1.0:paesslerag_gval/vendor/github.com/PaesslerAG/gval \
		ProtonMail:go-crypto:a4f6767435ab:protonmail_go_crypto/vendor/github.com/ProtonMail/go-crypto \
		acomagu:bufpipe:v1.0.3:acomagu_bufpipe/vendor/github.com/acomagu/bufpipe \
		agext:levenshtein:v1.2.3:agext_levenshtein/vendor/github.com/agext/levenshtein \
		antihax:optional:v1.0.0:antihax_optional/vendor/github.com/antihax/optional \
		avast:retry-go:v3.0.0:avast_retry_go/vendor/github.com/avast/retry-go \
		certifi:gocertifi:431795d63e8d:certifi_gocertifi/vendor/github.com/certifi/gocertifi \
		cirruslabs:cirrus-ci-agent:v1.77.3:cirruslabs_cirrus_ci_agent/vendor/github.com/cirruslabs/cirrus-ci-agent \
		cirruslabs:echelon:v1.7.0:cirruslabs_echelon/vendor/github.com/cirruslabs/echelon \
		cirruslabs:go-java-glob:v0.1.0:cirruslabs_go_java_glob/vendor/github.com/cirruslabs/go-java-glob \
		cirruslabs:podmanapi:v0.2.0:cirruslabs_podmanapi/vendor/github.com/cirruslabs/podmanapi \
		containerd:containerd:v1.5.3:containerd_containerd/vendor/github.com/containerd/containerd \
		containerd:ttrpc:v1.0.2:containerd_ttrpc/vendor/github.com/containerd/ttrpc \
		containerd:typeurl:v1.0.2:containerd_typeurl/vendor/github.com/containerd/typeurl \
		containers:image:v5.9.0:containers_image_v5/vendor/github.com/containers/image/v5 \
		containers:storage:v1.24.4:containers_storage/vendor/github.com/containers/storage \
		cyphar:filepath-securejoin:v0.2.2:cyphar_filepath_securejoin/vendor/github.com/cyphar/filepath-securejoin \
		davecgh:go-spew:v1.1.1:davecgh_go_spew/vendor/github.com/davecgh/go-spew \
		docker:cli:v20.10.7:docker_cli/vendor/github.com/docker/cli \
		docker:distribution:v2.7.1:docker_distribution/vendor/github.com/docker/distribution \
		docker:go-connections:v0.4.0:docker_go_connections/vendor/github.com/docker/go-connections \
		docker:go-units:v0.4.0:docker_go_units/vendor/github.com/docker/go-units \
		dustin:go-humanize:v1.0.0:dustin_go_humanize/vendor/github.com/dustin/go-humanize \
		emirpasic:gods:v1.12.0:emirpasic_gods/vendor/github.com/emirpasic/gods \
		fsnotify:fsnotify:v1.4.9:fsnotify_fsnotify/vendor/github.com/fsnotify/fsnotify \
		go-git:gcfg:v1.5.0:go_git_gcfg/vendor/github.com/go-git/gcfg \
		go-git:go-billy:v5.3.1:go_git_go_billy_v5/vendor/github.com/go-git/go-billy/v5 \
		go-git:go-git:a5bbcd278ab1:go_git_go_git_v5/vendor/github.com/go-git/go-git/v5 \
		go-ini:ini:v1.62.0:go_ini_ini/vendor/gopkg.in/ini.v1 \
		go-test:deep:v1.0.1:go_test_deep/vendor/github.com/go-test/deep \
		go-warnings:warnings:v0.1.2:go_warnings_warnings/vendor/gopkg.in/warnings.v0 \
		go-yaml:yaml:eeeca48fe776:go_yaml_yaml_1/vendor/gopkg.in/yaml.v3 \
		go-yaml:yaml:v2.4.0:go_yaml_yaml/vendor/gopkg.in/yaml.v2 \
		gogo:protobuf:v1.3.2:gogo_protobuf/vendor/github.com/gogo/protobuf \
		golang:appengine:v1.6.7:golang_appengine/vendor/google.golang.org/appengine \
		golang:crypto:e495a2d5b3d3:golang_crypto/vendor/golang.org/x/crypto \
		golang:net:5cfca573fb4d:golang_net/vendor/golang.org/x/net \
		golang:oauth2:08078c50e5b5:golang_oauth2/vendor/golang.org/x/oauth2 \
		golang:protobuf:v1.5.2:golang_protobuf/vendor/github.com/golang/protobuf \
		golang:sync:036812b2e83c:golang_sync/vendor/golang.org/x/sync \
		golang:sys:1d35b9e2eb4e:golang_sys/vendor/golang.org/x/sys \
		golang:text:v0.3.7:golang_text/vendor/golang.org/x/text \
		google:go-genproto:2b146023228c:google_go_genproto/vendor/google.golang.org/genproto \
		google:go-github:v32.1.0:google_go_github_v32/vendor/github.com/google/go-github/v32 \
		google:go-querystring:v1.0.0:google_go_querystring/vendor/github.com/google/go-querystring \
		google:shlex:e7afc7fbc510:google_shlex/vendor/github.com/google/shlex \
		google:starlark-go:7a1108eaa012:google_starlark_go/vendor/go.starlark.net \
		google:uuid:v1.3.0:google_uuid/vendor/github.com/google/uuid \
		grpc-ecosystem:go-grpc-middleware:v1.3.0:grpc_ecosystem_go_grpc_middleware/vendor/github.com/grpc-ecosystem/go-grpc-middleware \
		grpc:grpc-go:v1.41.0:grpc_grpc_go/vendor/google.golang.org/grpc \
		hashicorp:go-version:v1.3.0:hashicorp_go_version/vendor/github.com/hashicorp/go-version \
		hashicorp:golang-lru:v0.5.4:hashicorp_golang_lru/vendor/github.com/hashicorp/golang-lru \
		hashicorp:hcl:v1.0.0:hashicorp_hcl/vendor/github.com/hashicorp/hcl \
		imdario:mergo:v0.3.12:imdario_mergo/vendor/github.com/imdario/mergo \
		inconshreveable:mousetrap:v1.0.0:inconshreveable_mousetrap/vendor/github.com/inconshreveable/mousetrap \
		jbenet:go-context:d14ea06fba99:jbenet_go_context/vendor/github.com/jbenet/go-context \
		kevinburke:ssh_config:v1.1.0:kevinburke_ssh_config/vendor/github.com/kevinburke/ssh_config \
		klauspost:compress:v1.13.6:klauspost_compress/vendor/github.com/klauspost/compress \
		kr:fs:v0.1.0:kr_fs/vendor/github.com/kr/fs \
		lestrrat-go:jspointer:82fadba7561c:lestrrat_go_jspointer/vendor/github.com/lestrrat-go/jspointer \
		lestrrat-go:jsref:1b590508f37d:lestrrat_go_jsref/vendor/github.com/lestrrat-go/jsref \
		lestrrat-go:jsschema:5c81c58ffcc3:lestrrat_go_jsschema/vendor/github.com/lestrrat-go/jsschema \
		lestrrat-go:jsval:20277e9befc0:lestrrat_go_jsval/vendor/github.com/lestrrat-go/jsval \
		lestrrat-go:pdebug:4d6bd78da58d:lestrrat_go_pdebug/vendor/github.com/lestrrat-go/pdebug \
		lestrrat-go:structinfo:acd51874663b:lestrrat_go_structinfo/vendor/github.com/lestrrat-go/structinfo \
		magiconair:properties:v1.8.4:magiconair_properties/vendor/github.com/magiconair/properties \
		mitchellh:go-homedir:v1.1.0:mitchellh_go_homedir/vendor/github.com/mitchellh/go-homedir \
		mitchellh:go-ps:v1.0.0:mitchellh_go_ps/vendor/github.com/mitchellh/go-ps \
		mitchellh:mapstructure:v1.4.0:mitchellh_mapstructure/vendor/github.com/mitchellh/mapstructure \
		moby:buildkit:v0.9.0:moby_buildkit/vendor/github.com/moby/buildkit \
		moby:locker:v1.0.1:moby_locker/vendor/github.com/moby/locker \
		moby:moby:v0.6.3:moby_moby_1/vendor/github.com/docker/docker-credential-helpers \
		moby:moby:v20.10.7:moby_moby/vendor/github.com/docker/docker \
		moby:sys:mountinfo/v0.4.1:moby_sys_mountinfo/vendor/github.com/moby/sys \
		moby:term:df9cb8a40635:moby_term/vendor/github.com/moby/term \
		natefinch:lumberjack:v2.0.0:natefinch_lumberjack/vendor/gopkg.in/natefinch/lumberjack.v2 \
		onsi:ginkgo:v1.14.2:onsi_ginkgo/vendor/github.com/onsi/ginkgo \
		opencontainers:go-digest:v1.0.0:opencontainers_go_digest/vendor/github.com/opencontainers/go-digest \
		opencontainers:image-spec:775207bd45b6:opencontainers_image_spec/vendor/github.com/opencontainers/image-spec \
		opencontainers:runc:v1.0.0-rc93:opencontainers_runc/vendor/github.com/opencontainers/runc \
		opencontainers:runtime-spec:e6143ca7d51d:opencontainers_runtime_spec/vendor/github.com/opencontainers/runtime-spec \
		otiai10:copy:v1.7.0:otiai10_copy/vendor/github.com/otiai10/copy \
		pelletier:go-toml:v1.9.1:pelletier_go_toml/vendor/github.com/pelletier/go-toml \
		pkg:errors:v0.9.1:pkg_errors/vendor/github.com/pkg/errors \
		pkg:sftp:v1.12.0:pkg_sftp/vendor/github.com/pkg/sftp \
		pmezard:go-difflib:v1.0.0:pmezard_go_difflib/vendor/github.com/pmezard/go-difflib \
		protocolbuffers:protobuf-go:v1.27.1:protocolbuffers_protobuf_go/vendor/google.golang.org/protobuf \
		qri-io:starlib:v0.5.0:qri_io_starlib/vendor/github.com/qri-io/starlib \
		sergi:go-diff:v1.2.0:sergi_go_diff/vendor/github.com/sergi/go-diff \
		sirupsen:logrus:v1.8.1:sirupsen_logrus/vendor/github.com/sirupsen/logrus \
		spf13:afero:v1.5.1:spf13_afero/vendor/github.com/spf13/afero \
		spf13:cast:v1.3.1:spf13_cast/vendor/github.com/spf13/cast \
		spf13:cobra:v1.1.3:spf13_cobra/vendor/github.com/spf13/cobra \
		spf13:jwalterweatherman:v1.1.0:spf13_jwalterweatherman/vendor/github.com/spf13/jwalterweatherman \
		spf13:pflag:v1.0.5:spf13_pflag/vendor/github.com/spf13/pflag \
		spf13:viper:v1.7.1:spf13_viper/vendor/github.com/spf13/viper \
		stretchr:testify:v1.7.0:stretchr_testify/vendor/github.com/stretchr/testify \
		subosito:gotenv:v1.2.0:subosito_gotenv/vendor/github.com/subosito/gotenv \
		syndtr:gocapability:42c35b437635:syndtr_gocapability/vendor/github.com/syndtr/gocapability \
		xanzy:ssh-agent:v0.3.1:xanzy_ssh_agent/vendor/github.com/xanzy/ssh-agent \
		xeipuuv:gojsonpointer:df4f5c81cb3b:xeipuuv_gojsonpointer/vendor/github.com/xeipuuv/gojsonpointer \
		xeipuuv:gojsonreference:bd5ef7bd5415:xeipuuv_gojsonreference/vendor/github.com/xeipuuv/gojsonreference \
		xeipuuv:gojsonschema:v1.2.0:xeipuuv_gojsonschema/vendor/github.com/xeipuuv/gojsonschema \
		yudai:gojsondiff:v1.0.0:yudai_gojsondiff/vendor/github.com/yudai/gojsondiff \
		yudai:golcs:ecda9a501e82:yudai_golcs/vendor/github.com/yudai/golcs \
		yudai:pp:v2.0.1:yudai_pp/vendor/github.com/yudai/pp
GO_TARGET=	./cmd/cirrus

PLIST_FILES=	bin/cirrus

.include <bsd.port.mk>
