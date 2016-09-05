UPGRADE FROM 1.11 to 1.12
=========================

# OroSearchBundle
- Introduced new interface Oro\Bundle\SearchBundle\Engine\IndexerInterface. Next methods were extracted from
  Oro\Bundle\SearchBundle\Engine\EngineInterface into this new interface: `save`, `delete`, `reindex`.
- Configuration parameter **realtime_update** and container parameter `oro_search.realtime_update` were removed. All index operations are async now.
- Oro/Bundle/SearchBundle/Entity/UpdateEntity and Oro/Bundle/SearchBundle/EventListener/UpdateSchemaDoctrineListener were removed
- `oro_search.search.engine.indexer` service was replaced with async implementation `oro_search.async.indexer`. Use sync indexer only for test environment.
- New helper trait Oro/Component/Testing/SearchExtensionTrait - easy access to sync indexer for test environment

- The method OroCRM\Bundle\ChannelBundle\EventListener\UpdateIntegrationConnectorsListener::onChannelSucceedSave was renamed to onChannelSave
- The method OroCRM\Bundle\MagentoBundle\EventListener\UpdateIntegrationConnectorsListener::onChannelSucceedSave was renamed to onChannelSave
- The class OroCRM\Bundle\ChannelBundle\EventListener\ChangeChannelStatusListener was renamed to ChangeIntegrationStatusListener
- The class OroCRM\Bundle\ChannelBundle\EventListener\ChannelSaveSucceedListener was renamed to UpdateIntegrationConnectorsListener
- The class OroCRM\Bundle\MagentoBundle\EventListener\ChannelSaveSucceedListener was renamed to UpdateIntegrationConnectorsListener

